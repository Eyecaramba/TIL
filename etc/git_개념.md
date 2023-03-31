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

    checkout : 이전 버전 작업을 불러 오는 것 

    branch : 여러 명이 같은 코드를 공유하고 협업해야 하는 상황인 경우 각 개발자들은 여러 커밋을 통해 코드를 발전시킴. 이 때 누가 어떤 커밋을 추가했는지 구분이 가능해야 한다. 이때 사용되는 개념이 branch 

    merge : 나눈 branch를 하나의 branch로 합하는 것  

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
    
    (2) git에 commit하기 
    >> git commit -m 'commit 설명'

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

### 5. 실험적인 버전 만들기 
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
<br>



## 3. 유용한 명령어들 
____

    (1) 현재 hash값 클립보드에 가져오기 
    >> git rev-parse

    (2) ... 계속 작성중... 



