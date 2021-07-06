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
> > 1.4.1 Overview of Delay in Packet-Switched Networks
> >
> > - Processing Delay : 패킷의 header를 조사하고, 어디로 가야할 지를 정할 때 생기는 지연.
> > - Queuing Delay : 다음 목적지로 가는 링크로 전송되기 위해 기다릴 때 생기는 지연.
> > - Transmission Delay : 링크의 전송 비율에 의해 생기는 지연.
> > - Propagation Delay : 패킷이 링크를 따라 전파될 때 생기는 지연.
