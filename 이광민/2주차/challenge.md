## git-flow 란 무엇인지 정리
### git-flow란 5종류의 브랜치가 존재한다.
- master : 제품으로 출시될 수 있는 브랜치
- develop : 다음 출시 버전을 개발하는 브랜치
- feature : 기능을 개발하는 브랜치
- release : 이번 출시 버전을 준비하는 브랜치
- hotfix : 출시 버전에서 발생한 버그를 수정 하는 브랜치

![image](https://user-images.githubusercontent.com/43610417/224452355-ac4f7101-8d09-4f64-a748-251fac0acea0.png)

기본적으로 master와 develop 브랜치가 존재하며 develop 브랜치는 master에서 시작된 브랜치이다.

develop브래치에서는 상시로 버그를 수정한 커밋들이 추가되며 기능 추가가 있는 경우 develop브랜치에서 feature 브랜치를 생성한다.

그렇기 때문에 feature 브랜치는 언제나 develop 브랜치에서부터 시작한다.

모든 기능이 완성된다면 QA를 하기 위해 develop에서 release브랜치를 생성하며 QA를 진행하며 발생된 버그는 release브랜치에 수정된다.

## git 대표적 명령어 정리
### git 사용 법
저장소 복제하기

- git clone <저장소 url>

새로운 파일을 추가하거나 존재하는 파일 스테이징하고 커밋하기

- git add <파일>

- git commit -m “<메시지>”

파일의 일부를 스테이징하기

- git add -p [<파일> [<파일> [기타 파일들…]]]

수정되고 추적되는 모든 파일의 변경 사항 커밋하기

- git commit -m “<메시지>” -a

작업 트리의 변경 사항 돌려놓기

- git checkout HEAD <파일> [<파일>]

커밋되지 않고 스테이징된 변경 사항 재설정하기

- git reset HEAD <파일> [<파일>]

마지막 커밋 고치기

- git commit -m “<메시지>” - -amend
### git 브랜치

지역 브랜치 목록 보기

- git branch

원격 브랜치 목록 보기

- git branch -r

지역과 원격을 포함한 모든 브랜치 목록 보기

- git branch -a

현재 브랜치에서 새로운 브랜치 생성하기

- git branch <새로운 브랜치>

다른 브랜치 체크아웃하기

- git checkout <브랜치>

현재 브랜치에서 새로운 브랜치 생성하고 체크아웃하기

- git checkout -b <새로운 브랜치>

다른 시작 지점에서 브랜치 생성하기

- git branch <새로운 브랜치> <브랜치를 생성할 위치>

기존의 브랜치를 새로운 브랜치로 덮어쓰기

- git branch -f <기존 브랜치> [<브랜치를 생성할 위치>]

<새로운 브랜치>가 존재하지 않을 경우

- git checkout -m <기존 브랜치> <새로운 브랜치>

무조건 덮어쓰기

- git checkout -M <기존 브랜치> <새로운 브랜치>

다른 브랜치를 현재 브랜치로 합치기

- git merge <브랜치>

커밋하지 않고 합치기

- git merge - -no-commit <브랜치>

선택하여 합치기

- git cherry-pick <커밋명>

커밋하지 않고 선택하여 합치기

- git cherry-pick -n <커밋명>

브랜치의 이력을 다른 브랜치에 합치기

- git merge - -squash <브랜치>

삭제할 브랜치가 현재 브랜치에 합쳐졌을 경우에만 브랜치 삭제하기

- git branch -d <삭제할 브랜치>

삭제할 브랜치가 현재 브랜치에 합쳐지지 않았어도 브랜치 삭제하기

- git branch -D <삭제할 브랜치>

모든 이력 보기

- git log

변경 사항을 보여주는 패치와 함께 로그 표시하기

- git log -p

1개의 항목만 보이도록 로그 개수 제한하기

- git log -1

20개의 항목과 패치만 보이도록 로그 제한하기

- git log -20 -p

6개월 동안의 커밋 로그 보기

- git log - -since=”6 hours”

이틀 전까지의 커밋 로그 보기

- git log - -before=”2 days”

origin 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기

- git fetch

원격 저장소에서 합치지 않고 지역 브랜치로 변경 사항 가져오기

- git fetch <원격 저장소>

원격 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기

- git pull <원격 저장소>

origin 저장소에서 변경 사항을 가져와 현재 브랜치에 합치기

- git pull

지역 브랜치를 원격 브랜치에 푸싱하기

- git push <원격 저장소> <지역 브랜치>:<원격 브랜치>

지역 브랜치를 동일한 이름의 원격 브랜치에 푸싱하기

- git push <원격 저장소> <지역 브랜치>

새로운 로컬 브랜치를 원격 저장소에 푸싱하기

- git push <원격 저장소> <지역 브랜치>

원격 저장소에서 쓸모가 없어진 원격 브랜치 제거하기

- git remote prune <원격 저장소>

## MySQL에서 DB 테이블 설계시 중요 요소 각 정리
### 무결성 - 데이터베이스 내에 모든 값은 언제나 정확한 값을 유지해야 한다.
### 유연성 - 데이터베이스 구조는 요구사항 변화에 대해 수정이 쉬워야 한다.
### 확장성 - 데이터베이스 구조는 기능 확장에 대해서 수정이 쉬워야 한다.
1. 각 이름은 의미 있는 단어를 쓰며 단어들을 구분시에는 _ 을 사용한다.
2. 프로젝트의 이름을 축약한 이름으로 한다.
  - Base Multi Web : bmw
3. 테이블의 시작은 t_ 를 사용하며 뷰는 v_ 로 시작한다.
  -  t_board - 테이블, v_board - 뷰
4. 컬럼의 이름은 f_ 로 시작하며 추가적인 접미사는 일관된 이름을 사용한다.
  - xx명 : f_xxxx_nm
  - xx번호 : f_xxxx_no 
