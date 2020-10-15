# TCP/IP Protocol

### Overview

TCP/IP protocol is a protocol commonly used for device communications in Internet. But it can be also used in a private network such as intranet or extranet.

### TCP/IP Model

In TCP/IP protocol, there are four layers, applicaition layer, transport layer, internet layer and datalink layer. The data from a sender is basically broken down into a group of tiny packets and sent through the TCP/IP model layers. And when it is arrived in a receiver, the chunks of the packets are reconstructed into the original data and it would be consumed by the receiver (See Figure 1).

<div>
    <img src="./out/tcp-ip-model/TCP IP Protocol Model.png">
    <p>
        <strong>Fig.1</strong>
        A diagram how the data is transferred from a sender to the receiver in the TCP/IP model
    </p>
</div>

### TCP/IP 3-Way Handshake

In TCP/IP protocol, the handshake to establish the communication between two parties is called 3-way handshake. First of all a client will send a Syn signal. And upon the receipt of the Sync signal on a server side, it respond to the client with Ack-Syn signal. After that, if the client receives the Ack-Syn and respond to the server back with the Ack signal, the connection between the two will be established. And until the communication is terminated by either side, the parties can have an open communication channel and keep transferring and receiving data betwee each other.

<div>
    <img src="./out/tcp-ip-handshake/sequence diagram.png">
    <p>
        <strong>Fig.2</strong>
        A sequence diagram to show the TCP/IP protocol connection
    </p>
</div>

### References
- https://www.avast.com/c-what-is-tcp-ip
- https://searchnetworking.techtarget.com/definition/TCP-IP