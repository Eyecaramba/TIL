# 3. 트랜스포트 계층




http란?  

hyper text transfer protocol

hyper text : hyper text 전에는 text였다. text를 주고 받던 세상에서 
텍스트를 하나 다 보여주고 읽는 것만 가능했지 그 안에서 다시 다른 곳으로 넘어가는 개념은 없었다. 
이런 개념이 생겨나면서 hyper text라는 개념이 생겨났다.  
transfer : 
protocol : 약속 

html은 hyper text를 표현하기 위한 language이다.  
html을 주고 받을 수 있는 protocol이 http이다. 

url이란? : uniform resource locator(주소) 인터넷 주소를 의미한다.  <- uri와 다른 점은?

dns server : domain name server
DNS server는 domain에 해당하는 ip를 모두 가지고 있다. 
domain이 오면 해당 ip를 돌려주는 역할을 한다.  

ip란? : internet protocol 인터넷 주소다. ip를 이용해서 해당 장치를 찾아 간다. 
ip는 인터넷 서비스 공급자인 isp가 공급한다. 
(서버에 여러 웹사이트가 있을 수 있다 이 경우 ip에 추가적으로 host header 정보가 들어가야 한다.)

http에는 명령이 있다. 
get, put, post, delete
이런 명령들을 주고 받으며 우리가 보는 인터넷이 작동한다. 

RESTful이란? 
crud : create read update delete를 db에서 사용하는 개념  

REST라고 표현하기도 함. (예전에는 soap을 사용했으나 이제는 사용하지 않는다)
REpresentational State Transfer : 상태를 표현하는 전송이다. 
crud와 비슷하다. db에 읽고, 생성하고, 수정하고 지우겠다는 것이다. 어플리케이션에서는 이런 일들을 한다.

web에서도 이런 것을 하겠다는 것이다. web을 통해 resource의 상태를 제어하는 것이다. 
rest를 구성한다는 것은 client가 api를 통해 server에서 resource를 제어할 수 있도록 만드는 것이다. 

인터넷은 어떻게 구성되어 있는가? 
국제 표준은 7개지만 5개의 계층을 사용하고 있다. 
application : 
transport(수송 계층) : tcp, udp (end to end 개념이다.)
수송 계층이 하는 일은 무엇인가? 어플리케이션의 대리인으로 데이터를 전달해준다. 
이것 이외에 어떤 일은 하는 가는 어플리케이션이 무엇을 요구하는가에 따라 달라진다. 

network : 
경로를 찾는다. 

link : 
physical : 

web browser에서 get or post 같은 




RESTful이란? 
url : 





AJAX : 메뉴만 눌렀을 때 전체를 업데이트 하는 것이 아니라 

동기 함수 : 함수를 호출하면 함수가 값을 리턴하기 전까지 다음 행으로 넘어가지 않음 

비동기 함수 : 함수가 호출만 되면 바로 다음으로 넘어가는 함수 
그 결과는 콜백으로 다시 받는다. 

쿠키, 세션 : 변수를 저장하는 것 

쿠키 : 클라이언트의 일정 부분에 남는다. 
세션 : 웹 서버에 저장되어 있는 것 
(세션이 날라갔다)

VOIP : 음성을 데이터로 만들고 ip로 전달, 데이터를 음성으로 바꾸어 전달해준다.


tcp : 정확한 데이터를 목표로 한다. 
udp : 정확한 데이터가 가지 않을 수 있다. 

압축도 손실 무손실이 있다. 
정확하게 압축되고 정확히 
손실 : mpeg : 약간 깨지더라도 괜찮은 것들 (영상, 음성 등등)을 압축할 때 사용하는 것 


ip : 주소 
port : 항구 

한국에서 인천항으로 가는가 부산항으로 가는가에 해당하는 개념이 항구
항구에서 기다리는 어플리케이션이 모두 다르다. 
예시 : HTTP를 다루는 포트는 80번을 사용한다.
서버, 컴퓨터 포트를 검색하는 명령어 : netstat -n  


ip address : 숫자 
우리는 단어로 홈페이지 주소를 안다. 
그러나 컴퓨터는 알 수 없다. 
dns 서버는 이름을 숫자로 바꾸어 준다. 
목적지까지 가도록 만들어 주는 것이 IP
데이터를 전달 해 주는 것이 TCP 
이 둘을 합쳐서 TCP/IP 라고 한다. 

ip를 찾아가는 경로를 라우팅이라고 한다. 
라우터 장비 -> 전달을 위한 장비 
기본적으로 IPV4 0.0.0.0 
IPV6가 요즘 나오고 있다. 

NAT 서버 : 네트워크 어드레스 트랜스레이션
모든 서버가 퍼블릭 IP를 가지고 있지는 않다. 
라우터 안에 PRIVATE ROUTER를 사용한다. 

PRIVATE ROUTER는 밖에서 접근하지 못한다.  

송신지와 수신지가 있어야 하는데 
PRIVATE IP를 public ip로 바꿔줘야 한다. 
이를 nat 서버가 해준다. 


네트워크와 관련된 명령어 
ipconfig : 자신의 컴퓨터에 할당받은 ip 주소를 볼 수 있다. 
ping  + 주소 : 서버 컴퓨터가 잘 응답하는지 볼 수 있음 
tracert : url을 주면 해당 url을 가는 라우터를 확인할 수 있다. 
nslookup : 해당 도메인의 ip를 반환한다.   


이더넷 : 가장 물리적 하단에 있는 접속과 관련된 것 

인터넷 : 

허브 : 컴퓨터들이 유선으로 연결되어 있는 경우 모든 컴퓨터를 연결해주는 것 

http : 
https : http + 보안 (기본적으로 암호화 통신을 한다.)

전자 서명 : 이 데이터가 원본이라는 것을 알려주는 것 
전자 인증 : 내가 사용하는 이용자임을 알려주는 것
