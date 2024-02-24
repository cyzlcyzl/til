# TCP/IP 프로토콜 집합

## TCP/IP 프로토콜 계층

|||
|--|--|
| Application Layer | HTTP, FTP, SNMP.. |
| Transport Layer | TCP, UDP |
| Interner Layer | IP, ARP, ICMP, IGMP |
| Network Interface Layer | Ethenet, Token Ring.. |

### 1. Network Interface Layer
TCP/IP 패킷을 전송 매체에서 TCP/IP 패킷을 받아들이는 기능 담당

### 2. Internet Layer
인터넷 주소 부여, 패킹의 생성, 라우팅 기능을 제공
#### 2-1. IP (Internet Protocol)
`비연결형` 프로토콜이라고도 하며 인터넷 상에서 한 컴퓨터에서 다른 컴퓨터로 데이터를 보내기 위해 사용하는 프로토콜이다. 패킷 단위로 데이터를 전달한다.  

- `비연결성` : 패킷을 받을 대상이 없거나, 서비스 불능 상태여도 패킷을 전송  
- `비신뢰성` : 데이터 전송 순서를 보장하지 않으며, 중간에 패킷이 실종되어도 알 수 없음  

가장 광범위하게 사용되는 버전은 `IPv4`이지만 `IPv6` 역시 사용되기 시작하고 있다.  

### 3. Transport Layer
Application Layer에 연결형과 비연결형 통신 서비스를 제공하는 핵심 프로토콜
#### 3-1. TCP (Transmission Control Protocol)
- 연결 지향
  * `3 way handshake` : 클라이언트와 서버 모두 준비가 되었는지 연결하는 과정이라고 할 수 있다.  
  (1) 클라이언트에서 서버로 SYN  
  (2) 서버에서 클라이언트로 SYN + ACK  
  (3) 클라이언트에서 서버로 ACK  

  * `가상 회선`

- 데이터 전달 보증
- 순서 보장

#### 3-2. UDP (User Datagram Protocol)
`비접속형` 프로토콜로 데이터 전송시 어떠한 신뢰성이나 순서를 보장하지 못한다. 한마디로 `IP`와 흡사하나 `PORT`와 체크섬이라는 차이점이 존재한다.  

`UDP`는 `TCP`가 제공하는 서비스 전부를 필요로 하지 않은 경우에 사용한다. `TCP` 같은 경우엔 연결을 지향하고 있기 때문에 데이터의 길이도 길 뿐만 아니라 속도가 `UDP`에 비해 느릴 수밖에 없다. `HTTP3`에서 성능 개선을 위해 `UDP`를 쓰면서 `UDP`가 각광 받고 있으나 `TCP`가 압도적으로 많다.

### 4. Application Layer
다른 계층의 서비스에 접근할 수 있게 하는 애플리케이션을 제공하고 애플리케이션들이 데이터를 교환하기 위해 사용하는 프로토콜로 HTTP, FTP, SMTP, Telnet 등이 있으며 계속 새로운 프로토콜이 개발되고 있다.  
  
    
----  

> 참고  
_모든 개발자를 위한 HTTP 기본 지식 (김영한)_  
_네트워크 프로그래밍 (김우완 지음)_



 

