---
Title: Computer Networking Lecture 4
Status: 
marker: 
tags: 
Date: 2024-07-23
Time: 12:13
---
# Index
- [OSI Reference Model (Open System Interconnection)](#osi-reference-model-open-system-interconnection)
- [The Seven Layers of the OSI Model](#the-seven-layers-of-the-osi-model)
  - [Physical Layer (Layer 1)](#physical-layer-layer-1)
  - [Data Link Layer (Layer 2)](#data-link-layer-layer-2)
  - [Network Layer (Layer 3)](#network-layer-layer-3)
  - [Transport Layer (Layer 4)](#transport-layer-layer-4)
  - [Session Layer (Layer 5)](#session-layer-layer-5)
  - [Presentation Layer (Layer 6)](#presentation-layer-layer-6)
  - [Application Layer (Layer 7)](#application-layer-layer-7)
- [Importance of the OSI Model](#importance-of-the-osi-model)
- [TCP/IP Reference Model](#tcpip-reference-model)
- [Layers of the TCP/IP Reference Model](#layers-of-the-tcpip-reference-model)
  - [Network Interface Layer (Link Layer)](#network-interface-layer-link-layer)
  - [Internet Layer](#internet-layer)
  - [Transport Layer](#transport-layer)
  - [Application Layer](#application-layer)
- [Comparison with OSI Model](#comparison-with-osi-model)
- [Key Protocols and Their Functions](#key-protocols-and-their-functions)
  - [IP (Internet Protocol)](#ip-internet-protocol)
  - [TCP (Transmission Control Protocol)](#tcp-transmission-control-protocol)
  - [UDP (User Datagram Protocol)](#udp-user-datagram-protocol)
  - [HTTP (HyperText Transfer Protocol)](#http-hypertext-transfer-protocol)
  - [FTP (File Transfer Protocol)](#ftp-file-transfer-protocol)
  - [SMTP (Simple Mail Transfer Protocol)](#smtp-simple-mail-transfer-protocol)
  - [DNS (Domain Name System)](#dns-domain-name-system)
- [Importance of the TCP/IP Model](#importance-of-the-tcpip-model)
- [Private Public Ports etc](#private-public-ports-etc)
- [Sockets](#sockets)
- [Ports](#ports)
- [HTTP/S](#https)
- [Communication](#communication)
- [Layers 7 Layer 4 Layer](#layers-7-layer-4-layer)
- [References](#references)
# Content

## OSI Reference Model ( Open System Interconnection )
![[OSI Reference Model.excalidraw]]
The OSI (Open Systems Interconnection) model is a conceptual framework used to understand and standardize the functions of a telecommunication or computing system without regard to its underlying internal structure and technology. The model is divided into seven layers, each specifying particular network functions.

### The Seven Layers of the OSI Model

1. **Physical Layer (Layer 1)**:
   - Deals with the physical connection between devices and the transmission and reception of raw bit streams over a physical medium.
   - Examples: Ethernet cables, Hubs.

2. **Data Link Layer (Layer 2)**:
   - Provides node-to-node data transfer and handles error correction from the physical layer.
   - Examples: Switches, Bridges, MAC addresses.

3. **Network Layer (Layer 3)**:
   - Manages data routing, forwarding, and addressing, enabling data to be sent from source to destination across multiple networks.
   - Examples: Routers, IP addresses.

4. **Transport Layer (Layer 4)**:
   - Ensures end-to-end communication, error recovery, and flow control.
   - Examples: TCP (Transmission Control Protocol), UDP (User Datagram Protocol).

5. **Session Layer (Layer 5)**:
   - Manages sessions or connections between applications, establishing, maintaining, and terminating connections.
   - Examples: Session establishment, maintenance, and termination protocols.

6. **Presentation Layer (Layer 6)**:
   - Translates data between the application layer and the network format, handling data encryption, compression, and translation.
   - Examples: Encryption (SSL/TLS), data compression.

7. **Application Layer (Layer 7)**:
   - Provides network services directly to user applications, facilitating communication with other applications over the network.
   - Examples: HTTP, FTP, SMTP, DNS.

### Importance of the OSI Model

- **Standardization**: Provides a universal set of standards for networking, ensuring interoperability between different systems and technologies.
- **Modularity**: Each layer is independent, so changes in one layer do not necessarily affect the others, making network management more efficient.
- **Troubleshooting**: Helps in diagnosing and fixing network issues by isolating problems within specific layers.
- **Education**: Aids in teaching and understanding how networks operate, providing a clear framework for studying and developing networking technologies.

By dividing network communication into these seven distinct layers, the OSI model simplifies the process of designing and implementing network protocols, ensuring that diverse systems can communicate effectively.

## TCP/IP

	![[TCP IP Ref Model.excalidraw.md]]

The TCP/IP reference model, also known as the Internet Protocol Suite, is a set of communication protocols used to interconnect network devices on the internet. It provides end-to-end data communication, specifying how data should be packetized, addressed, transmitted, routed, and received at the destination. The TCP/IP model simplifies network communication by dividing it into four layers, each responsible for different aspects of the communication process.

### Layers of the TCP/IP Reference Model

1. **Network Interface Layer (Link Layer)**
   - **Function**: Responsible for the physical transmission of data over a network. It defines protocols for how data is sent and received on the physical medium (like Ethernet).
   - **Protocols and Technologies**: Ethernet, Wi-Fi, ARP (Address Resolution Protocol), PPP (Point-to-Point Protocol).
   - **Components**: Network interface cards (NICs), cables, switches, and other hardware.

2. **Internet Layer**
   - **Function**: Handles the logical addressing and routing of data packets. It is responsible for moving packets from the source to the destination across multiple networks.
   - **Protocols**: IP (Internet Protocol), ICMP (Internet Control Message Protocol), ARP (Address Resolution Protocol), and RARP (Reverse Address Resolution Protocol).
   - **Components**: Routers, gateways.

3. **Transport Layer**
   - **Function**: Provides end-to-end communication, error detection and correction, and ensures that data is delivered in the correct order and without errors.
   - **Protocols**: TCP (Transmission Control Protocol) for reliable communication, and UDP (User Datagram Protocol) for connectionless communication.
   - **Components**: Hosts, end systems, applications.

4. **Application Layer**
   - **Function**: Contains protocols and services that support network applications. It provides services directly to the user's application processes, such as email, file transfer, and web browsing.
   - **Protocols**: HTTP (HyperText Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System), Telnet, SSH.
   - **Components**: Application software and network services.

### Comparison with OSI Model

The TCP/IP model is often compared to the OSI model, which has seven layers. Here are some key differences:

- **Layer Mapping**: The TCP/IP model has four layers, while the OSI model has seven layers. Some OSI layers are combined in the TCP/IP model (e.g., the OSI's Application, Presentation, and Session layers are combined into the TCP/IP Application layer).
- **Development**: The TCP/IP model was developed earlier and is based on standard protocols used on the internet, whereas the OSI model was developed as a theoretical framework.
- **Adoption**: The TCP/IP model is the basis for the Internet and is widely adopted, while the OSI model is more of a guideline and is used for teaching and conceptual understanding.

### Key Protocols and Their Functions

- **IP (Internet Protocol)**: Provides logical addressing and routing. It is responsible for packetizing data, adding addressing information, and ensuring that packets are routed correctly to their destination.
- **TCP (Transmission Control Protocol)**: Provides reliable, ordered, and error-checked delivery of a stream of bytes. It establishes a connection between the sender and receiver before data can be sent.
- **UDP (User Datagram Protocol)**: Provides a connectionless service for applications that do not require reliable delivery. It is used for tasks such as streaming audio and video.
- **HTTP (HyperText Transfer Protocol)**: Used for transferring web pages on the internet.
- **FTP (File Transfer Protocol)**: Used for transferring files between computers on a network.
- **SMTP (Simple Mail Transfer Protocol)**: Used for sending emails.
- **DNS (Domain Name System)**: Translates human-readable domain names into IP addresses.

### Importance of the TCP/IP Model

- **Standardization**: Provides a standardized set of protocols that ensures different devices and networks can communicate with each other.
- **Interoperability**: Ensures that various hardware and software components from different manufacturers can work together.
- **Scalability**: Supports a vast and growing network like the Internet, accommodating billions of devices.
- **Flexibility**: Allows for the integration of new technologies and protocols as the network evolves.

The TCP/IP model has been instrumental in the development and expansion of the internet, providing a robust and adaptable framework for network communication.

## Private Public Ports etc

## Sockets
## Ports
## HTTP/S
## Communication

## Layers 7 Layer 4 Layer


# References
