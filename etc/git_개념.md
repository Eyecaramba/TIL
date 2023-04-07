## git
_______  

__*intro*__  
git에 관한 내용 계속 작성중... 

__목차__

    1. git 개념
    2. git의 전반적인 사용방법  
    3. 유용한 명령어 


## 1. git의 개념 
____

git  
    
    분산형 버전 관리 시스템  

    (버전 관리 : 특정 시점의 버전을 다시 꺼내올 수 있는 시스템)

    git은 여러 명이 하나의 문서를 가지고 작업을 하더라도 각자 수정한 버전들을 업로드 할 수 있다.

    따라서 버그가 발생한 경우 빠르게 버그를 찾아낼 수 있다. 

    여러 명이 동시에 작업할 수 있기 때문에 병렬 개발이 가능하다. 

    팀 프로젝트가 아니더라도 체계적인 개발이 가능하다. 


git 용어  

    repository : remote, local 두 가지 있음

    working dirctory (working tree) : 사용자가 현재 편집하고 있는 버전
    
    snapshot : 특정 시점에서 파일, 폴더 또는 워크 스페이스의 상태를 의미함  

    git에서 commit을 실행하면 스냅샷이 저장된다. 

    staging area : 커밋을 준비하는 위치 (특정 파일만 버전으로 만들고 싶을 수 있기 때문에 위 단계를 만들어 놓음)

    commit : 현재 변경된 작업 상태 점검을 마치면 확정하고 저장소에 저장하는 작업  

    checkout : head의 시간여행

    branch : 여러 명이 같은 코드를 공유하고 협업해야 하는 상황인 경우 각 개발자들은 여러 커밋을 통해 코드를 발전시킴. 이 때 누가 어떤 커밋을 추가했는지 구분이 가능해야 한다. 이때 사용되는 개념이 branch 

    merge : 나눈 branch를 하나의 branch로 합하는 것  

github 

    pull request 

<br>  

## 1. git의 전반적인 사용방법 
______


### __1.__  github에서 repo 생성 및 local에 작업환경 만들기    
<br>  

    - github에서 repo 만들기 

    - github에 생성된 repo의 https주소 복사하기 

    - Local 터미널에서 다음과 같이 입력
    >> git clone '복사한 https 주소'
<br>  
<br>  
  
### __2.__ Local 초기 설정하기  
<br>  


    git을 local에서 처음 사용하는 경우 터미널에서 다음과 같은 설정이 필요합니다.  

    (1) github 가입 이름 설정하기 
    >> git config --global user.name 'github 이름'  
    
    (2) github 가입 이메일 설정하기 
    >> git config --global user.email 'github 이메일'  
<br>  

### 3. Local에서 작업한 내용 git에 반영하기   
<br>  
  
    터미널에서 다음과 같은 작업을 해줍니다.  

    (1) git stage에 작업했던 파일 올리기 
    >> git add '작업파일'
    
    add 명령어는 'Untracked'상태를 'Tracked'로 바꿔준다. 
    'Modified'는 add된 적이 있는 파일을 의미한다.   
    
    절대 공유해서는 안되는 파일 또한 존재한다.  
    '.gitignore' 파일을 만들고 이 안에 파일이름을 저장해 놓으면 Tracked 상태로 변하지 않고 commite도 되지 않는다.  
    '.gitignore'파일은 무엇을 commit하면 안되는지 알려주는 정책이기 때문에 이 파일은 commit해야한다.  
 
    (2) git에 commit하기 
    >> git commit -m 'commit 설명'

    add 과정 없이 commit 하기 
    >> git commit -am 'commit 설명'
    위 명령어는 modified 상태인 파일만을 commit한다. untracked된 상태는 commit하지 않는다. 

    새로운 commit을 하고 싶은 만들고 싶은 것이 아니라 마지막 버전을 변환하여 저장하고 싶은 경우 
    >> git commit -amend -m 'commit 설명'

    (3) github에 올리기 
    >> git push origin main 

<br>  

### 4. git commit history 확인하기 
<br>  

    git log 명령어를 통해 commit history를 확인할 수 있으며 다양한 옵션을 사용할 수 있다.  
    
    (1) git log 확인하기 
    >> git log 

    (2) git log history를 한 줄로 보여줌 
    >> git log --oneline

    (3) git commit history와 함께 main, head가 어디에 있는지 모두 보여준다. 
    >> git log --all

    (4) git의 전반적인 모습을 그래프로 보여준다.  
    >> git log --graph
<br>  

### 5. 실험적인 버전 만들기 & 새로운 branch 만들기 
<br>

    (1) head와 main이 따로 움직이도록 만들기 
    >> git checkout 'commit hash'  

    (2) checkout한 상태에서 commit하기 
    >> git commit -m 'commit 내용'

    (3-1) 실험이 실패한 경우 : main으로 돌아오기 
    >> git checkout main

    (3-2) 실험을 계속해서 이어나가고 싶은 경우 : branch로 만들기 
    >> git branch 'branch 이름'

    (3-2) 실험에 성공한 경우 : main branch로 돌아와서 다른 branch와 합치기  
    >> git checkout main
    >> git merge '합치고자 하는 branch 이름'

    merge는 기본적으로 3자 대면을 시키는 명령어이다.  
    버전 A와 버전 B와 합쳐지는 경우 '버전 A', '버전 B', '버전 A와 B의 공통 조상'이 서로 만난다. 
    (버전 A만 변경된 내용 + 버전 B만 변경된 내용 + 변경되지 않은 내용)은 자동으로 합쳐주지만 (서로 다르게 변경된 내용)은 conflict를 발생시키고 어떤 내용으로 수정할지는 사용자가 선택해야 한다.  
<br>
  
### 6. git branch 
<br>

    (1) branch 만들기 
    >> git branch 'branch 이름'

    (2) branch 옮기기 
    >> git reset --hard <current branch> to <해당 commit>
    head가 가리키는 커밋에서 git reset 사용시 
    head가 가리키지 않는 커밋에서 git reset 사용시 git checkout과 효과가 같다.  

    (3) github에 branch 만들기 
    >> git push --set-upstream origin 'branch name'
<br>


### 7. git으로 협업하기 
<br> 

    (1) git pull (= git fetch & git merge)
    git pull을 하여 최신 repo 상태를 받는다.  
 
    (2) 충돌 해결하기 

    (3) 작업하기 

    (4) git commit & git push 
    - github에 origin

    (5) pull request (= merge request)
    -  origin과 작업중인 branch와의 병합이 필요한 경우 pull request를 하면 된다.  
    - request에서는 origin과의 충돌을 계속해서 보여준다. 이를 계속해서 해결해 나가야 나중에 고생을 덜한다. 


## 3. 유용한 명령어들 
____

    (1) 현재 hash값 클립보드에 가져오기 
    >> git rev-parse

    (2) git 단축 명령어 생성하기  
    >> git config --global alia.<단축 명령어> <원래 명령어>  
    예시 : 'git log --online -all --graph' -> 'git l' 로 만들기    
    >> git config --global alias.l 'log --online -all --graph' 

    (3) git config pull.rebase false  

    (4) git의 참조 로그 확인하기 
    >> git reflog 
    (실수로 삭제한 commit을 다시 되돌리고 싶은 경우 commit id가 필요한데 이를 확인하는데 유용하다.)
