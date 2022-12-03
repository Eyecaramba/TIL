# git 

## 0. git? 

- git : 분산형 버전 관리 시스템  
(버전 관리 : 특정 시점의 버전을 다시 꺼내올 수 있는 시스템)

git은 여러 명이 하나의 문서를 가지고 작업을 하더라도 각자 수정한 버전들을 업로드 할 수 있다.  

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

## branch

여러 명이 같은 코드를 공유하고 협업해야 하는 상황인 경우 각 개발자들은 여러 커밋을 통해 코드를 발전시킴. 이 때 누가 어떤 커밋을 추가했는지 구분이 가능해야 한다. 이때 사용되는 개념이 branch 

- 명령어  
__git branch__ : git branch list 보기   
__git branch__ 'brach_name' : 새로운 branch 생성   
__git checkout__ 'branch_name' : 다른 branch로 이동

## merge 

나눈 branch를 하나의 branch로 합하는 것  




merge : 내용을 현재 branch로 가져와 합치는 작업  



- git 명령어 



