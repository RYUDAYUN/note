## Network
---
#### TCP
- 가상 회선 연결 방식, 연결형 서비스
- 높은 신뢰성
- 흐름제어 및 혼잡제어

#### UDP
- 비연결형 서비스
- 사용자 데이터그램형 프로토콜
- 신호절차를 거치지 않고 보내는 쪽에서 일방적으로 데이터를 전달하는 통신 프로토콜
- 비신뢰성
- 패킷 오버헤드가 적어 네트워크 부하 감소

###### TCP 3-way Handshake
- 논리적인 접속을 성립하기 위한 방법
- 과정
  - step 1: 클라이언트는 서버에 접속을 요청하는 SYN 패킷을 보냄. 그리고 서버의 응답을 기다림
  - step 2: 서버는 클라이언트에게 요청을 수락하는 패킷을 발송함. 그리고 클라이언트의 응답을 기다림
  - step 3: 클라이언트는 서버에게 ACK 신호를 보내고 이후로부터는 연결이 이루어진 상태

#### IP
- Internet Protocol
- OSI 네트워크 계층에서 호스트의 주소지저과 패킷 분할 및 조립 기능을 담당.

#### OSI 7계층
하단부 부터

층|layer | Data 단위
---|---|---
1|physical| Bit
2|Data Link|Frame
3|Network|Packet
4|Transport|segments
5|Session|Data
6|Presentation|Data
7|Application|Data
