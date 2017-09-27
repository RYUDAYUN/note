# IoT networking in the IoT
#### 2017 9월 25일
---
###  IoT : Internet는 TCP/IP사용 ,Things는 TCP/IP사용X->번역이 필요

### Network Module
- WSN
  - Multi-hop communication
  - 무선의 특징
  - 자신의 데이터만 전달하는것이 x 이전 노드것까지 포워딩 시켜서 전달
  - 모든 노드가 라우터 역할까지 다함.
  - ex) 교통사고 : 사고가 나게 된것을 뒷차에게 전달 -> 사고가 났기때문에 속도를 줄여라, 모빌리티(GPS)

>포워딩 ? 라우터를 통해서

- MANET
- WMN : 미국 경우는 시골 외곽지역에서 많이 사용
- VANET
---
##### Management
- packet
- Address : 보내는 사람 ,받는 사람의 주소 Payload
- device

---
##### Routing Technologies
- Dijkstra's algorithm : 자기 자신을 제외한 모든노드로 최단 경로를 계산하는 방법
- Link State Routing
- Open shortest Path First (OSPF)
  - 인터넷에서 가장 많이 사용
  - 라우팅 테이블 만드는 방법 : 라우터들이 연결된 정보를 나머지에게 다 알려줌(link state packet), 모든 정보를 갖고 미리 계산을 해둠.
  - Dj 알고리즘을 사용하여 만듦
  - IoT에게 적용하긴 오버헤드가 너무 큼.
- DSDV

#### Routing in wireless Mobile Networks vs. in Traditional NEtworks
- 주소에 대해서 고정되어 있지 않다.
- Redundant data traffic , 중복된 데이터
- source는 여러개인데 destination이 한개인 문제(because 모든 데이터는 게이트웨이로 전송되기 때문에)
- 결론적으론 새로운 라우팅 프로토콜을 개발해야 한다.

#### Common Routing Techiques in Wireless & Mobile
- Distance Vector
- Link State : 기존의 것을 최대한 활용
  - 문제점: 자기정보를 모두 전달 있는것으로 하는데, IoT는 배터리 전력
- Path Vector : 이웃에게만 전달, 전달 받은 정보로 계산을 함
- Flooding : broadcast로 통신, 데이터가 무선통신 범위에 퍼지게 됨
- source Routing : 기본 가정은 각 노드가 ID가부여, 경로를 같이 부여 (패킷헤더안에)

---
#### 2017 9월 27일

#### Route Establishment & Maintenance
- Proactive (table-driven) : 주기적으로 무선적으로 테이블 만드는것.
- Reactive (on-demend) : 테이블을 만드지 않는 것, Route discovery를 함. 경로를 먼저 찾음. 그 다음 경로를 통해서 전달
- mixed : 위 두가지 섞은 것.


#### Wireless Networking (Routing) in IoT
1. Flooding :
  만약 A가 H에게 전달하고 싶으면 broadcast함.(A가 보낸것임을 정보를 포함)
2. Source Routing:
  - 데이터를 보낼때 경로를 지정해서 보냄. (Broadcast)
  - Dynamic Source Routing 리액티브 방식, 데이터를 보낼때 라우팅 테이블을 새로 만듦, Route discovery 과정을 통해서 결정 -> Delivery
  - Route Discovery in DSR : 자기 아이디를 써나가면서 broadcast, RREQ를 받았으면 RREP를 보냄
  - DSR 성능을 향상시키 위해서 Caching 사용
  - AODV : RREQ를 먼저 보냄, 자기아이디를 추가적으로 넣어서 전달 X, S와 몇홉이 떨어져있는지 , 누구한테 받았는지  To S, 2 hop, via E
4. IPv6 Routing Protocol for Low-Power and Lossy Networks
  - RPL : "Ripple(잔물결)" routing protocol , DAG의 개념을 가지고 만듦.
  - DIO 메세지를 broadcast 함. rank를 만듦.
  > DAG : Directed Acyclic Graphs (방향성이 있는 싸이클없는 그래프)

  - P2MP(Point-to-Multi-Point) for Downward traffic
  - Point-to-Point(P2P) : Downward + Upward


  #### Network Performance
  - Power supply: 얼마나 에너지를 소모하게 하는가?(최소인게 좋음)
  - Power Consumption
  - Position of a gateway

  #### Network Flow & Qos - aware Protocol

  - Energy Aware Qos Routing Protocol : 라우팅의 배터리정보까지 포함해서 라우팅 경로를 짬.
  
