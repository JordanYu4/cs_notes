## Transport layer 

- Allows multiple applications to use same network connection 
- Opens ~65,000 ports on computer to be reserved and used 

#### Workflow 
- Application sends message through port, which is wrapped in segment on transfer layer 
    - Segment indicates source and destination port  
- Message arrives on destination machine, transferred from network layer to transport layer 
- Message is unwrapped and delivered to destination port 

#### Transport protocols: TCP v. UDP 
UDP 
- User Datagram Protocol
- Lightweight, but unreliable 
- Advantages 
    - Small packet sizes (8 bytes v. 20 bytes)
    - No connection required to create and maintain 
    - More control over when data is sent 
- Disadvantages 
    - Primitive error detection: 16 bit checksum (unreliable)
        - Won't attempt recovery from data corruption 
        - Discards or flags corrupted packets
    - No guarantee of in-order arrival 
    - No congestion control 
        - Packages more likely to be dropped on crowded network 
TCP 
- Transmission Control Protocol 
- Reliable, connection-based (more overhead)
- Setting up connection: 3-way handshake to open and close connections 
    - TCP segments carry number 
- Source continues to send until receipt acknowledgement received 
- Advantages
    - Numbered segments enable sorting prior to application receipt 
    - Congestion control - delays transmission when network congested 
    - Error detection - not improved, but checksum mandatory for IPv4 and IPv6
- Disadvantages 
    - Bigger header (~60% larger than UDP)
    - Data not guaranteed to be sent immediately due to congestion control 
        - Use case: real time exchanges like video or phone call 
    - Bigger overhead 
        - Retransmission of packets, acknowledgements of packets 
        - Video streaming has ways of compensating for packet loss 
Messages v. streams 
- UDP - message-oriented 
    - App sends data in distinct chunks 
    - Metaphor: snail mail, email, text messaging 
- TCP - stream
    - Continuous flow of data 
    - App agnostic of data packeting, TCP handles depending on network conditions 
    -  Metaphor: phone convo 

#### Use cases 
TCP
- Text communication 
- File transfers 
- Remote access (e.g. SSH)
- Delivery acknowledgement 
    - Acknowledgement system can be implemented for UDP in app layer, tho might not be worth it  
- Multimedia streaming when overhead doesn't diminish performance (high bandwidth) or firewalls blocking UDP 
UDP 
- Multimedia streaming 
- Instant sending required 
- Data loss can be masked 
- Bandwidth-intensive apps that can tolerate some packet loss 
- Low overhead 
- Small question/answer transactions (e.g. DNS lookups)

#### Terminology 
- IPv - Internet Protocol version 

#### Sources 
- [UDP and TCP: Comparison of Transport Protocols](https://www.youtube.com/watch?v=Vdc8TCESIg8)