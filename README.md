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
> >
> > #### 2.2.4 User-Server Interaction: Cookies
> >
> > - server에 처음 방문하는 client의 경우 server는 쿠키ID를 만들고, 데이터베이스에 해당 ID에 관한 엔트리를 저장한다.
> > - server는 http response message에 쿠키 헤더라인을 포함하여 보낸다.
> > - client는 쿠키파일에 해당 아이디를 저장하고, 다음 request message부터 쿠키 헤더라인을 포함하여 보낸다.
> > - server는 쿠키 ID에 해당하는 엔트리에 client의 history를 기록한다.
> >
> > #### 2.2.5 Web Caching
> >
> > - original server없이 client의 요청을 수행하기 위해 두는 장치. server와 같은 역할을 하여 proxy server라고 한다.
> > - client는 request를 original server에 보내지 않고 proxy server에 보낸다.
> > - 해당 요청에 관한 정보가 proxy server에 있다면 바로 응답을 해주고, 없다면 original server에 해당 요청에 대한 응답을 받아와 저장하고, 전해준다.
> > - ISP에 대한 access link에 대한 부하를 줄여 비용을 아낄 수 있다.
> > - original server까지 갈 필요가 없기때문에 속도 또한 빠르다.
> > - The Conditional GET
> >   - original server와 proxy server간에 데이터 불일치를 해결하기 위한 방법.
> >   - client는 request message에 해당 데이터가 수정된 날짜를 포함하여 original server로 보낸다.
> >   - original server는 해당 데이터의 수정된 날짜를 비교하여 같다면 304 Not Modified 메시지를 보내고, 이때 object는 포함하지 않는다.(access link의 부하를 줄이기 위해서이다.)
> >   - 다르다면 object를 포함하는 메시지를 보낸다.
>
> ### 2.3 Electronic Mail in the Internet
>
> - email의 세 가지 주요 요소
>
>   - user agents : 메일메시지를 쓰고, 수정하고, 읽는 applications.
>   - mail servers : mail box를 사용하여 유저의 메일을 받고, message queue를 사용하여 유저의 메시지를 보낸다.
>   - simple mail transfer protocol(SMTP) : 메시지를 주고 받을때, 사용하는 protocol.
>
> > #### 2.3.1 SMTP
> >
> > - TCP connection위에서 동작한다.
> > - 3단계로 구성된다.
> >   - handshaking : TCP connection을 한다.
> >   - transfer of messages : 전달할 object들을 전한다.
> >   - closure : TCP connection을 해제한다.
> >
> > #### 2.3.2 Comparison with HTTP
> >
> > - HTTP는 pull, SMTP는 push
> > - HTTP는 response message에 object 1개, SMTP는 여러 object를 보낸다.
> >
> > #### 2.3.4 Mail Access Protocols
> >
> > : receiver의 mailbox에서 메시지를 회수할 때, 사용하는 프로토콜.
> >
> > - POP3 : Download and Delete, Download and Keep 방식. client의 history가 기록되지 않는다.(어떤 메시지를 읽었는지 알 수 없다.)
> > - IMAP : client의 history를 기록하여 session을 유지한다.(메일을 어떤걸 읽었는지 등을 알 수 있다.)
>
> ### 2.4 DNS—The Internet’s Directory Service
>
> > #### 2.4.1 Services Provided by DNS
> >
> > - hostname을 IP주소로 바꿔준다.
> > - host에게 별명을 붙여준다.
> > - load를 분산시킨다.(하나의 hostname에 여러개의 서버들이 연결되어있는 경우)
> > - mail server에 별명을 붙여준다.
> >
> > #### 2.4.2 Overview of How DNS Works
> >
> > - A Distributed, Hierarchical Database : Root DNS, TLD DNS, Authorititive DNS순으로 계층을 이룬다.
> > - 각 DNS서버는 하위 DNS서버의 주소를 알고있다.
> > - Local DNS name server : 로컬에 위치한 proxy server.
> > - client가 hostname을 입력한다 -> Local DNS name server가 IP주소를 알고 있는 경우 바로 알려준다. -> 모른다면 Root DNS에 요청한다. -> TLD DNS로 요청한다. -> Authorititive DNS 요청하여 해당 host의 IP주소를 알아낸다.
> > - 위 과정에서 2가지 방식이 존재한다.
> >   - iterated query : 다음 계층의 DNS주소를 알려준다.
> >   - recursive query : 물어물어 실제 IP주소를 알려준다.
> > - DNS Caching : 한번 요청한 IP주소를 저장한다.보통 TLD서버들이 캐싱되고 따라서 Root name server에 대한 부하를 줄인다.
> > - DNS record : DNS server가 저장하는 기록. resource records가 있다. resource records는 hostname-to-IP address mappings을 기록한다.
> >   - type A : hostname to ip adress
> >   - type CNAME : alias name to canonical name(정식이름)
> >   - type NS : domain to hostname of authoritative name server
> >   - type MX : name to mail server
>
> ### 2.5 Peer-to-Peer File Distribution
>
> - 항시 가동되는 서버가 없다.
> - 임의의 end systems끼리 직접적으로 소통한다.
> - client - server architecture보다 속도가 빠르다. 각각의 peer들을 service capacity로 데려오기 때문.
>
> ### 2.6 Socket Programming with UDP and TCP
>
> - Sockey Programming with UDP
>   - client와 server사이에 connection을 필요로 하지 않는다.
>   - sender는 각 패킷에 자기의 IP주소와 포트번호를 명시한다.(connection이 없기 때문이며, 이 작업은 운영체제가 수행한다.)
>   - receiver는 패킷에서 sender의 IP주소와 포트번호를 추출한다.
>   - 데이터가 손실될 수도, 순서가 바뀔 수도 있다.
> - Socket Programming with TCP
>   - server에서는 client를 받기위한 socket(welcomes client's contact)이 존재한다.
>   - client는 TCP socket을 생성하고 server TCP와 connection을 한다.
>   - server TCP는 client를 위한 socket을 생성하고 여기를 통해 communication을 한다.
>   - 데이터 전송이 안정적이고, 순서유지가 된다.
>
> ## Chapter 3 Transport Layer
>
> ### 3.1 tranport-layer services
>
> - Transport services and protocols
>   - 다른 host에서 실행중인 프로세스 사이의 논리적인 의사소통을 제공한다.
>   - transport protocols은 end system에서 실행된다.(TCP, UDP)
>     - send side : app messages를 segments로 나누고 network layer로 보낸다.
>     - rcv side : segments를 messages로 재조립하고 app layer로 보낸다.
> - Transport VS network layer
>   - network layer : 호스트들 사이의 의사소통.
>   - transport layer : 프로세스 사이의 의사소통.
>
> ### 3.2 multiplexing and demultiplexing
>
> - multiplexing / demultiplexing
>   - sender측에서는 여러 프로세스들에서 오는 데이터들을 하나의 묶어서 보낸다.
>   - receiver측에서는 묶여서 보내진 데이터를 풀어서 필요로하는 프로세스로 보낸다.
> - Connectionless demultiplexing
>   - sender측에서는 UDP segment에 목적지 IP주소와 포트번호를 명시한다.
>   - receiver측에서는 segment에서 포트 번호를 확인하고 해당 번호를 가지는 socket으로 보낸다.
> - Connection - oriented demultiplexing
>   - TCP socket은 source ip address, source port number, dest ip address, dest port number 이 4가지 값에 의해 식별된다.
>
> ### 3.3 Connectionless transport : UDP
>
> : 별도의 connection없이 메시지를 보내는 프토토콜. 메시지는 중간에 잃어버리거나, 순서가 바뀔수도 있다. 약간의 손실이 큰 지장을 주지 않는 서비스에 사용된다. 예를들면 스트리밍 서비스가 있다. 간단하고, 헤더사이즈가 작으며, flow controll, congestion controll이 없어 바라는 만큼 메시지를 보낼 수 있다. application 자체에서 에러에 대한 대비를 한다면 오히려 유용할 수도 있다.
>
> - UDP segment format
>   - source port #
>   - destination port #
>   - length
>   - checksum
>   - application data
>
> ### 3.4 Principles of reliable data transfer
>
> - checksum : 받은 데이터의 에러를 확인하는 변수.
> - Acknowledgement : 이전까지는 잘 받았고, 이제 받고자 하는 번호.
> - Negative acknowledgement : 잘못된 데이터를 받은 경우 보낸다.
> - Timer : ack을 받기위해 기다리는 시간. ack이 도착하지 않으면 해당 데이터를 다시 보낸다.
> - Window : ack을 받지 않은 데이터를 얼마만큼 보내도 되는지를 나타내는 변수.
> - Pipelining : connection을 최대로 활용하기 위해 데이터를 계속해서 보낸다.
> - Sequence number : 적제된 데이터의 첫번째 비트가 몇번째 순서인지 나타내는 번호.
>
> ### 3.5 Connection - oriented transport : TCP
>
> : connection 기반의 프토토콜. 메시지 전송에 대해 안정적이며, 순서유지가 가능하고, 네트워크 흐름, 혼잡을 제어할 수 있다. segment 헤더가 크다.
>
> - TCP segment structure
>   - sequence number : message의 순서. 중복으로 같은 메시지를 받는것을 예방하기도 한다.
>   - acknowledgements : 다음에 받아야 하는 sequence number. 이전까지의 메시지는 잘 받은 상태.
>   - Timeout
>     - acknowledgement를 기다리다가 설정된 시간이 지나면 메시지를 재전송 한다.
>     - RTT보다 길게 잡는다.
>     - 너무 짧으면 불필요한 재전송이 많이 발생하게 되고, 너무 길면 segment손실에 대해 반응이 느리다.
> - Reliable data transfer
>   - TCP sender events
>     - app 계층으로부터 데이터를 받고, segment를 만들고, seq#를 부여하고, 타이머가 꺼져있다면 타이머를 시작시킨다.
>     - ack을 받는 시간이 초과했다면 segment를 재전송한다.
>     - ack을 받으면, 업데이트를 하고, 타이머를 재조정한다.
>   - TCP receiver events
>     - segment의 순서대로 도착하고, 모든 데이터에 대한 ack을 이미 보낸경우 -> 500ms정도 기다린다.(모아서 보내기 위해)
>     - segment의 순서대로 도착하고, 이전 segment가 ack을 보류하고 있는경우 -> 즉시 묶어서 ack을 보낸다.
>     - segment의 순서대로 도착하지 않아서 gap이 생긴경우 -> 즉시 duplicate ack을 보낸다.
>     - gap의 시작부분을 채우는 segment가 도착한 경우 -> 즉시 ack을 보낸다.
>   - TCP fast retransmit
>     - 만약 같은 데이터에 대한 3번의 duplicate ack을 받는다면 time-out시간 안에도 그 즉시 데이터를 재전송한다.(drop이 되었다고 판단. 지연이 길어지는 것을 방지하기 위함)
> - Flow controll
>   - tranport계층에서 application계층으로 데이터가 전달될 때, receiver측에서는 TCP socket receiver buffer에 데이터를 잠시 저장된다. 이때 buffer가 넘치면 데이터가 손실되므로 receiver측에서 버퍼의 남은 사이즈를 TCP segment header에 적어 보낸다. sender측에서는 버퍼 사이즈를 넘지 않는 경우에만 segment를 보낸다.
> - Connection Management
>   - 3-way handshake
>     1. client가 server로 요청한다.
>     2. server가 client의 요청을 확인한다.(client estb)
>     3. client가 server의 확인을 다시 확인한다.(server estb)
>   - closing a connection(4-way handshake)
>     1. client가 FINbit를 1로하고 연결해제를 요청한다.
>     2. server가 ack을 보낸다.
>     3. server는 마지막데이터를 보내고 FINbit를 1로하고 데이터전송이 끝났음을 알린다.
>     4. client가 ack을 보내고 일정시간이 지난 후 close한다.(이때 서버는 ack을 받으면 close한다.)
>
> ### 3.7 TCP Congestion control
>
> - additive increase multiplicative decrease : loss가 발견될때 까지 cwnd를 천천히 증가시키고, loss가 발견된다면 cwnd를 급격히 감소시킨다.
> - TCP Congestion Avoidance
>   - ssthresh : cwnd의 증가속도를 정하는 기준. cwnd < sstresh면, cwnd를 2배씩 증가시키고, cwnd > sstresh면 cwnd를 1개씩 증가시킨다. 만약 loss가 발생한다면 ssthresh를 cwnd/2로 줄인다.
> - TCP : detecting, reacting to loss
>   - TCP Tahoe : timeout, 3duplicate acks가 발생하면 cwnd를 1로, ssthresh를 반으로 줄인다.
>   - TCP RENO : timeout -> cwnd를 1로, 3duplicate acks -> cwnd, ssthresh를 반으로 줄인다.
> - TCP performance metric
>   - TCP throughput : 평균적으로 3/4 \* W/RTT가 나온다. 여기서 W는 loss가 발생하는 window size다.
>   - TCP Fairness : 같은 link를 사용하는 connection들이 공평하게 bandwidth를 사용하는 것.
>
> ## Chapter 4 Network Layer
>
> ### 4.1 Introduction
>
> - tranport계층에서 내려온 segment를 datagram으로 감싸서 receiving host로 보낸다.
> - receiving host에서는 전달된 segment를 tranport계층으로 보낸다.
> - network계층 protocol은 모든 host, router에 있다.
> - router는 datagram의 header를 조사하여 다음 목적지로 보낸다.
> - network계층의 핵심 기능 2가지
>   - forwarding : router의 input으로 들어온 패킷을 적절한 output으로 옮긴다.
>   - routing : 패킷이 전송될 경로를 정한다.
>
> ### 4.2 virtual circuit and datagram networks
>
> - virtual circuit : network layer connection service
>   - call setup : 목적지로 call을 보내면서 경로를 결정한다.
>   - 각 패킷은 vc식별자로 식별된다.
> - datagram : network layer connectionless service
>   - call setup단계가 존재하지 않는다.
>   - 목적지 주소에 의해 패킷은 내보내진다. 이때 구체적인 목적지 주소보다는 주소의 범위를 사용한다.
>
> ### 4.3 what's inside a router
>
> - Input port
>   - line speed에 맞춰 switching fabrics로 datagram을 forwarding하는 것을 목표로 한다.
>   - 만약 switching fabrics로 나가는 속도보다 datagram의 도착속도가 빠르면 queueing버퍼에 저장한다.
> - Switching fabrics
>   - input buffer의 패킷을 적절한 output buffer로 전달한다.
> - Output port
>   - switching fabrics에서 들어오는 datagram유입속도가 전송속도보다 빠르면 버퍼에 저장한다.
>   - 전송을 위해 버퍼에서 datagram을 고른다.(이때, 우선순위에 의해 순서가 바뀔수도 있다.)
>
> ### 4.4 IP : Internet Protocol
>
> - IP fragmentation, reassembly
>   - datagram의 크기가 network link의 전송사이즈를 넘어가면, datagram을 여러개의 fragment로 쪼개고 이를 destination에서 다시 조립한다.
> - IPv4 addressing
>   - subnet part와 host part로 이루어져 있다.
>   - subnet은 라우터를 거치지 않고 물리적으로 도달할 수 있는 범위이다.
> - DHCP(Dynamic Host Configuration Protocol)
>   - host가 network에 join할 때, server로부터 동적으로 IP주소를 획득하는 것을 목표로 한다.
>   - 주소를 일정기간동안 할당하고 회수한다.
>   - 주소의 재사용이 가능하다.
>   - host가 DHCP discover msg를 뿌린다. -> 이를 받은 DHCP server가 DHCP offer msg를 제공한다. -> host는 DHCP request msg를 보낸다. -> server는 DHCP ack msg를 보낸다.
> - NAT(Network Address Translation)
>   - local network와 outside network를 분리하여 local network내부에서는 임의로 IP주소를 사용하는 방식.
>   - ISP로부터 subnet을 할당받지 않아도 된다.
>   - local network내부의 변화를 outside network로 알리지 않아도 된다.
>   - ISP를 바꿀때도 문제가 없다.
>   - local network를 캡슐화 한다고 생각.
>   - 위의 것들이 가능하기 위해서 NAT router는 mapping table을 가져야 한다.
> - ICMP(internet control message protocol)
>   - host와 router사이의 소통을 위한 프로토콜. 에러 알림, 또는 핑퐁(req, res)에 주로 사용된다.
> - IPv6
>   - IPv4의 주소부족 문제를 해결하기 위해 나옴.
>   - IPv6는 datagram의 header size를 40byte로 고정하여 router내부에서 processing / forwarding 속도를 높였다.
>   - header에 flow label, priority를 추가하여 파일전송과 같은 작업의 Qos(Quality of service)를 유지하는데 용이하도록 하였다.
>     - priority : flow의 datagram중 우선순위 식별자.
>     - flow label : datagram이 같은 flow인지 아닌지를 식별한다.
>   - tunneling : IPv4에서 IPv6로 모든 라우터들을 동시에 변경하기는 현실적으로 불가능하기에 IPv6 datagram은 IPv4를 사용하는 router에 보내질 때, IPv4 datagram에 적재하여 보내진다.
>
> ### 4.5 routing algorithms
>
> - link state : 모든 라우터가 라우터들의 배치, 링크 cost를 알고있는 경우 사용하는 알고리즘.
>   - Dijkstra's algorithm
> - distance vector : 인접 라우터의 정보만을 알고있는 경우 사용하는 알고리즘.
>   - Bellman-Ford algorithm
>     - 인접노드의 거리벡터(다른 노드까지의 최단거리)를 이용해서 최단거리를 구하는 알고리즘
>     - 자신의 cost가 변하거나 인접노드의 거리벡터가 변하면 최단거리를 다시 계산한 후 broadcast.
>     - count to infinity(인접노드간에 변화를 계속해서 주고받는 상황)문제가 발생할 수 있다.
>     - poisoned reverse(경로가 X -> Y -> Z인 경우 Y가 Z로 가는 경로를 X에게 물어볼때 모른척 즉, 거리가 무한대라고 한다.)로 해결하지만 루프가 생기는 경우는 해결하지 못한다.
> - hierarchical routing
>   - link state, distance vector 알고리즘은 2가지 문제가 존재.
>   - 네트워크가 점점 커지면서 그 규모를 감당하기 힘들다.
>   - 관리 측면에서 각 지역단위로 네트워크를 관리하기를 원한다.
>   - 따라서 내부지역과 외부지역에 각각 라우팅 알고리즘을 적용한다.
>   - intra(내부) - AS(autonomous system) routing
>     - link state
>     - distance vector
>   - inter(외부) - AS routing
>     - gateway router(외부 AS와 연결되어 있는 라우터)를 통하여 외부 AS를 통해 갈 수 있는 정보를 받아온다.
>     - 받아온 정보를 내부 라우터에 전파한다.
