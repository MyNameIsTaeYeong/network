# Computer Networking

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
