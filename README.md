### CLI(Command Line Interface)

: 명령어를 통해 사용자와 컴퓨터가 상호작용하는 방식
- 직접 파일이름을 쳐야함.
- 서버프로그램은 CLI 사용
- 장점 :
    1. 메모리 적게 사용.
    2. 키보드만으로 작업수행 가능.
    3. 효율적으로 동작.

### GUI (Grachic User Interface)

: 그래픽을 통해 사용자와 컴퓨터가 상호작용하는 방식
- 마우스로 클릭
- 편함

#### CLI
- 커서 = 프롬프트
- exit 치면 닫힘
- 위에 view - terminal 누르면 됨
- ls 치면 로컬저장소 보여줌
- 깃배쉬에서 웬만하면 파일, 폴더 이름은 영어로, 띄어쓰기 없이, 언더바 사용
- 디렉토리는 폴더랑 비슷
- 점(.) = 현재 디렉토리
- 점 2개는 현재의 상위 디렉토리(상위폴더)
- cd (Change Directory)

- cd . 하면 현재 폴더.
- cd .. 하면 상위폴더로 감.
- 하위로 이동은 이름 쓰기.

예) cd 폴더1/폴더2,

상위의 상위는 cd ../..
- mkdir 폴더명 : 폴더 만들기
- touch a.txt : 저 이름과 형식의 파일 생김
- a 옵션은 all : 숨김파일까지 다 보임
- start a.txt : 실행
- code a.txt : 코드로 열기
- rm a.txt : 삭제
- rm -r 폴더명 : 폴더 삭제

---
- 내 위치 잘 알아야함
1. 절대경로 : pwd(print working directory) = 현재 작업위치를 root 디렉토리부터 모든 경로 다 보여줌
2. 상대경로 : 현재디렉토리 기준으로 상대적 위치 알려줌

## GIT (분산버전관리시스템)
- 버전 관리 : 변화를 기록, 추적 (롤백 가능)
- 완성본 + 각 버전의 변경사항
- 중앙집중식 : 중앙서버에 저장, 다시 중앙에 업로드
- 분산식 : 버전 여러 저장소에 저장 및 관리
1. 작업충돌 줄임, 생산성 향상
2. 백업 복구 용이
3. 인터넷 연결되지 않은 환경에서도 가능
4. 나중에 중앙서버와 동기화
5. 현실적으로 타 서버에 있는 거 확인해가면서 해야 함.

### git의 3가지 영역
1. **working directory (작업 디렉토리)** : 현재 작업중인 파일이 위치하는 영역
2. **staging area** : 변경된 파일 중 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간준비 영역.
3. **repository(저장소)** : 버전(commit : 버전을 찍는다) 이력과 파일들이 **영구저장**되는 영역, 모든 버전, 변경 이력 기록.
commit : 변경된 파일 저장하는 행위, 사진 찍듯 기록한다해서 snapshot이라함.

- **git init** : 로컬 저장소 설정(초기화), git의 버전관리 시작할 디렉에서 진행
- git add : 변경사항이 있는 파일을 staging area 에 추가. 예) git add a.txt 나 폴더명도 가능 git add a.txt, /layer1
- git add *.txt (메모장 파일 전부 스테이징에어리어에 올리는거)
- git add . : 모든 파일 다 올리는거
- git commit : staging area에 있는 파일들을 저장소에 기록, 해당시점 버전 생성하고 변경이력 남기는 거.  git commit -m “메시지 내용(변경된 내용)”

예)  git commit -m “login 기능 추가”

- *ls -a  : 숨김폴더도 보임*

- *ls : 로컬저장소 보여줌*
- 숨김폴더에 HEAD 봐두라하셨음
- master (master branch) ..? : ls -a 하고 보면 (master) 생겨져있는데 뭔지 나중에 알려주신대.
- 깃으로 관리하는 파일이면 그 파일 오른쪽에 어떤 상태인지 알려주는 U(untracked) 같은 알파벳 생김
- git status : 친절하게 지금 뭔 상태 같은 거 설명해줌
- git add sample.txt ---- **A** : s.a에 Added이란 뜻 ==>  .git 폴더에 있음

- ***unstage** : S.A에 안올리고 다시 워킹디렉에 내렸다는 뜻*

- git m --cached sample.txt
- git commit -m 'first commit'
- git add 파일명 꼭 하고 해야함
- git log로 레포지토리 뭐 볼 수 있음.
- git log --oneline   : 짧게 볼 수 있음.
- head : 깃발처럼 그림
- git status : 현재 로컬저장소의 파일상태 보기
- git log : commit history  보기
- git log --oneline : commit 목록 한줄보기
- git config --global -1 : 지금 설정되어있는 정보 볼 수 있음.
**1. git init 주의사항**
- git 로컬 저장소 내에 또다른 깃 로컬 저장소를 만들지 말 것.
- 즉, 이미 깃 로컬 저장소인 디렉 내부 하단에서 git init 명령어를 다시 입력하지 말 것. 
- git 저장소 안에 git저장소가 있을 경우 가장 바깥쪽의 git저장소가 안쪽의 깃 저장소의 변경사항을 추적할 수 없기 때문.
- 이렇게 되면 지우면 됨. .git 폴더를 삭제! => rm -r .git/  => ls -a

- 마스터 브랜치가 없을 때 git init 하면 안됨. (?)

- 상위폴더 올라가서 git init 하면 안된다는고.

- til 폴더 구조 만드는 데에는 정답 없음.
- 여러 개발자들의 깃헙 방문해서 참고해보기

## 바로 직전 생성한 commit 수정하기
1. commit 메세지 수정
2. commit 전체 수정

- ?
- commit hash 값 확인
- git commit --amend 하고, 메세지 수정하고 나갈 때는 **esc + : wq + enter**

- 실수로 파일 하나 b_function.txt를 빼고 commit 해버린 상황.
- b_function.txt 파일 생성
- b_function.txt 파일 s.a에 추가.

>> ls -a , touch b_function.txt, git add ., git add README.md, git status, git log --onelind, git commit --amend, i치고 수정하고 나오고 

# 2024.07.12.

## 원격 저장소

: 코드와 버전관리이력을 온라인 상의 특정 위치에 저장하여 여러 개발자가 협업하고 코드를 공유할 수 있는 저장공간

- 깃허브 레포지토리——— remote 관계 ——- 로컬 레포지토리
- git **remote** **add** *origin* remote_repo_url  :  로컬 저장소에 원격 저장소 추가(연결)
- origin 부분 다른거 써도 되는데 저렇게 쓰는 게 개발자들 간 관행 : 커멘션
- origin : 별칭을 사용해 로컬에 여러개 만들 수 있음?
- git  **remote** **add** *origin* [first_repo.git](https://github.com/rckwon/first_repo.git)
- git remote -v : origin 이라는 이름을 가진 원격저장소의 위치를 알려줌

- push : 여기 url로 넣을거야~
- fetch (잡아채는 거) & merge : 가지고올 때 그 url로 가지고 올 거야~

- 깃헙 레포지로 가는건 push 로컬로 가는 건 pull&clone
- **git push origin master** : 원격저장소에 commit 목록을 업로드

== git아 push 해줘 origin이라는 이름의 원격저장소에 master라는 이름의 브랜치를.

- 이거 치면 sign in 하라는 브라우저 뜸
- 최초 푸쉬시에는 깃허브에서 인증.

- 커밋해서 깃허브저장소에 푸쉬하는거

: 내용 수정, 저장, $ git add .  > $ git commit -m 'version1’   >  $ git push origin master

- 원격저장소에는 커밋이 올라가는 것. 커밋 이력이 없다면 푸쉬할 수 없다.
- 수정, 저장, add, commit, push 가 세트

## pull & clone

- git pull origin master : 원격 저장소의 변경사항만을 받아옴 (업데이트 개념)
- git clone remote_repo_url : 원격저장소 전체를 복제해서 다운로드
- clone으로 받은 프로젝트는 이미 git init 되어있음!
- ???는 .git 폴더가 있으면 안된다????
- 뉴비 아무것도 없는데 받을 때는 clone?, 이미 있는 곳에 가지고 오는 거는 pull?

### 뉴비가 받을 때는

$ git clone http://github.com/rckwon/first_repo.git

$ cd first_repo

$ ls -a

$ git log --oneline

### pull 받을 때는

*cd desttop에서 파일명 같은거 수정*

*mv -f first_repo git_advanced : 폴더명 바꾸는거.*

**3년차가 수정. add push 이런거 하고.**

**뉴비가 git pull origin master**

## 실습1. 원격 저장소에 push하기

1. 새로운 폴더생성 후 로컬 저장소 설정 : git init
2. commit 목록 생성 : git commit -m ‘~~’
3. 새로운 github 레포 생성 : 깃허브에서 만들기
4. 원격 저장소 추가 : git remote add origin url
5. commit 목록 push : git push origin master

## 실습2. 로컬 저장소 하나에 여러 원격 저장소 추가

1. 기존에 오리진 추가한 로컬저장소에 이어서 진행
2. 새로운 git hub레포 생성 : 깃허브에서 third_repo 만들기
3. origin 이 아닌 다른 이름으로 원격 저장소 추가  : $ git remote add eunchae https://github.com/rckwon/third_repo.git
4. commit 목록 push : git add, commit하고 $ git push eunchae master

### 실습3. 3년차가 시작

1. 깃허브 만들고 $ git clone https://github.com/garam0107/word-repo.git
2. 해당 깃 세팅에서 컬래버레이터? 거기서 가람님 추가
3. cd Desktop > mkdir wordrelay > cd workrelay > git init > touch word.txt > 만들고 > git add . >  git commit -m ‘1.권은채’
4. $ git remote add origin https://github.com/rckwon/wordrelay.git
5. $ git push origin master

## 뉴비는

1. $ git clone https://github.com/garam0107/word-repo.git
2. cd wordrelay
3. $ git add word.txt
4. 끝말잇기 추가
5. git add . > git commit -m '2.채소’
6. $ git push origin master