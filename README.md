# Computer Networking

```
참고한 책

Computer Networking

A Top-Down Approach

Seventh Edition

James F. Kurose

University of Massachusetts, Amherst

Keith W. Ross

NYU and NYU Shanghai
```

> ## Chapter 1 Computer Networks and the Internet
>
> - Internet : network of networks.
> - protocols : internet에서 메시지를 보내고 받는 방식.
>
> ### 1.2 The Network Edge
>
> > - End System(=Host) : 스마트폰, 데스크톱과 같이 네크워크의 가장자리에서 사용되는 시스템.
> > - router : End System으로부터 들어온 데이터를 전달하는 장치.
> > - comunication links : router, end system들을 물리적으로 연결해주는 회선.
> > - Access Networks : End System을 first router(edge router)에 물리적으로 연결하는 네트워크
> >   - Access Network를 특징짓는 중요 파라미터
> >     - bandwidth(trasmission rate) : 초당 실어나르는 비트 수(bps).
> >     - shared or dedicated?
> >   - Digital Subscriber Line(DSL) : 통신사에서 제공해주는 Access Network. dedicated line이다.
> >   - cable network : 케이블회사에서 제공하는 Access Network. share access network다.
>
> ### 1.3 The Network Core
>
> > 1.3.1 Packet Switching
> >
> > - 각 end system들이 메시지를 주고받을때, 메시지는 packet이라고 불리는 작은 chunk들로 쪼개진다.
> > - Store-and-Forward Transmission : packet switch들은 outbound link에 첫번째 packet을 전송하기 전에 전체 packet들을 받아야만 한다.
> > - Queuing Delays and Packet Loss
> >   - output buffer(output queue) : 패킷이 외부링크로 전송되기 전에 지연 또는 여러 상황에 의해 대기하는 곳.
> >   - queuing delays : 패킷전송 지연
> >   - packet loss : output buffer가 꽉 찼을 때 패킷이 드랍되는 현상.
> > - Forwarding Tables and Routing Protocols
> >   - Forwarding Table : packet의 목적지 주소와 외부로 나가는 link가 맵핑되어 있는 테이블.
> >   - Routing Protocol : 자동으로 Forwarding Table을 설정하는데 사용되는 절차.
>
> > 1.3.2 Circuit Switching
> >
> > - circuit : sender와 receiver사이의 connection.
> > - sender와 receiver사이의 통신을 위해 미리 자원을 예약한 후 독점하여 사용한다. 자원을 독점했기 때문에 일정한 속도를 보장한다.
>
> ### 1.4 Delay, Loss, and Throughput in Packet-Switched Networks
>
> : 네트워크의 퍼포먼스를 얘기할때, 가장 주요하게 생각하는 3가지 변수. Delay, Loss, and Throughput.
>
> > ### Delay
> >
> > - Processing Delay : 패킷의 header를 조사하고, 어디로 가야할 지를 정할 때 생기는 지연.
> > - Queuing Delay : 다음 목적지로 가는 링크로 전송되기 위해 기다릴 때 생기는 지연.
> > - Transmission Delay : 링크의 전송 비율에 의해 생기는 지연.
> > - Propagation Delay : 패킷이 링크를 따라 전파될 때 생기는 지연.
>
> > ### Loss
> >
> > - Buffer(queue)는 유한하기 때문에 만약 buffer가 꽉 차있을 때, 패킷이 도착한다면, 그 패킷은 drop된다.
>
> > ### Throughput
> >
> > - Sender와 Receiver사이에 전송되는 비율(bit/time)
> > - Bottleneck link : End to End throughput을 제한하는 링크. 전송 비율이 작은 링크를 의미한다.
>
> ### 1.5 Protocol layers
>
> > ### Internet protocol stack
> >
> > - application : network application을 지원(HTTP, FTM, SMTP)한다. application에서 발생하는 Message를 만든다.
> > - transport : Source process 와 Destination process사이에 데이터를 전송한다.
> > - network : Source host와 Destination host사이를 연결한다.
> > - link : 한 홉(node)를 연결한다.
> > - physical : wire에 bit를 집어넣는다.
>
> ### 1.6 Networks under attack : security
>
> > ### Malware
> >
> > - virus : 받고 실행하였을 때, 감염된다.
> > - worm : 받기만 하여도 감염된다. 스스로 실행하기 떄문.
>
> > ### botnet
> >
> > - 감염된 host
>
> > ### Denial of Service(DoS)
> >
> > - traffic을 증가시켜 resource를 이용가능하지 않도록 만든다.
> > - 타켓을 정하고, 타겟 주변 host들을 botnet으로 만들고, 타켓에 패킷을 보내 트래픽을 증가시킨다.
>
> > ### sniffing
> >
> > - Broadcast media(shared ethernet, wireless)에서 여러 사용자의 packet들을 읽거나 쓴다.
>
> > ### spoofing
> >
> > - 마치 다른 사용자가 메시지를 보낸 것처럼 위장한다.
>
> ## Chapter 2 Application Layer
>
> ### 2.1 Principles of Network Applications
>
> > #### 2.1.1 Network Application Architectures
> >
> > - Client - Server : 하나의 서버를 중심으로 여러 클라이언트들이 통신하는 구조.
> > - Ppeer to Peer(P2P) : End System들이 직접적으로 통신하는 구조.
>
> > #### 2.1.2 Processes Communicating
> >
> > - 같은 호스트인 경우는 process끼리 운영체제에 의해 통신한다.
> > - 다른 호스트인 경우 메시지를 교환하여 통신한다.
> > - Client - Server 구조인 경우
> >   - client process : 통신을 시작하는 프로세스.
> >   - server process : client process와 연결되기 위해 기다리는 프로세스.
> > - P2P구조인 경우 : 한 호스트에서 client, server process들을 다 가진다.
> > - Socket : Application계층과 Trasport계층이 메시지를 주고받는 문.
> > - Addressing Processes
> >   - 메시지를 받기위해서 프로세스는 식별자를 가져야 한다.
> >   - 호스트 장치는 고유한 32비트 ip주소를 가진다.
> >   - 한 호스트에는 여러 프로그램이 돌아가므로, 프로그램을 식별하기 위해서는 포트번호가 사용된다.
>
> > #### 2.1.3 Transport Services Available to Applications
> >
> > - Data integrity : 몇몇 앱은 100% 데이터가 전송되기를 원한다.
> > - Timing : 몇몇 앱은 낮은 delay를 필요로 한다.
> > - Throughput : 몇몇 앱은 최소한의 처리량을 필요로 한다.
> > - Security : 데이터 무결성, 암호화등
>
> > #### 2.1.4 Transport Services Provided by the Internet
> >
> > - TCP service : connection에 기반하여 데이터를 확실히 전송할 수 있고, 데이터 전송시 발생하는 에러사항들을 방지 할 수 있다.
> > - UDP service : 데이터 전송에 신뢰할 수 없지만 약간의 데이터 손실이 가능한 상황에서는 connection을 연결할 필요가 없는 장점이 있다.
> >
> > #### 2.1.5 Application-Layer Protocols
> >
> > - 교환되는 메시지 타입을 정의한다.(req, res)
> > - 메시지 문법을 정의한다.(field)
> > - 메시지 의미를 정의한다.
> > - 메시지를 주고받는 규칙을 정의한다.
>
> ### 2.2 The Web and HTTP
>
> - 웹페이지는 여러 Object들로 이루어져 있다.
> - Object는 HTML파일, 이미지파일등이 될 수 있다.
> - 웹페이지는 여러개의 참조되는 Object들을 포함하는 base - HTML file로 구성되어 있다.
> - 각 Object들은 URL에 의해 주소지정이 가능하다.
>
> > #### 2.2.1 Overview of HTTP
> >
> > - HTTP : hypertext tranfer protocol의 약어로 웹의 에플리케이션 계층에서 사용하는 protocol이다.
> >
> > #### 2.2.2 Non-Persistent and Persistent Connections
> >
> > - Non-Persistent HTTP
> >   - 많아야 한개의 object가 TCP connection에 의해 보내진다.
> >   - 그런 다음 connection이 닫힌다.
> >   - 여러개의 object들을 다운로드 하기위해서는 여러번의 connection을 필요로 한다.
> >   - connection의 의미는 client process와 server process가 메시지를 주고받을 수 있는 socket을 만든다는 것이다.
> > - RTT : 작은 패킷이 클라이언트에서 출발하여 서버에 갔다오는 시간. Non-Persistent HTTP는 object 1개를 보내는데 2RTT + 파일전송시간이 걸린다.
> > - Persistent HTTP
> > - connection을 유지한 체로 request와 response를 주고받는다.
> > - 모든 object들에 대하여 거의 RTT에 가까운 시간이 걸린다.
> >
> > #### 2.2.3 HTTP Message Format
> >
> > - request와 response 유형의 메시지가 있다.
> > - HTTP Request Message
> >   - request line, header lines, body로 이루어져 있다.
> >   - POST, GET유형의 업로드 방식이 있다.
> >   - POST방식은 input이 request message의 entity body에 추가되어 업로드된다.
> >   - GET방식은 input이 URL에 업로드된다.
> > - HTTP Response Message
> >   - status line, header lines, data로 이루어져 있다.
