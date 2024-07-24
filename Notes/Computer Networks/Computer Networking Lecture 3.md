---
Title: Signals & Systems lecture 3
Status: 
marker: 
tags: 
Date: 22-07-2024
Time: 10:22
---
# Computer Networking Lecture 3

## Index
- [Content](#content)
  - [How is File Saved in Memory Register](#how-is-file-saved-in-memory-register)
  - [Bits, Bytes, and Nibbles](#bits-bytes-and-nibbles)
  - [LSB, MSB](#lsb-msb)
  - [Intel and AMD](#intel-and-amd)
  - [Motorola Process](#motorola-process)
  - [ARM Processor](#arm-processor)
- [Endianness](##Endianness)
  - [Little Endian](#little-endian)
  - [Big Endian](#big-endian)
  - [Slab Servers](#slab-servers)
  - [Conversion of Little Endian to Big Endian](#conversion-of-little-endian-to-big-endian)
- [References](#references)

## Content

### How is File Saved in Memory Register
Files are saved in memory registers as a series of bytes. The operating system and file system manage how these bytes are allocated in memory. The data is stored in binary format, with each byte consisting of 8 bits. The sequence and structure of these bytes depend on the file format and the architecture of the system (such as little-endian or big-endian).

### Bits, Bytes, and Nibbles
- **Bit:** The smallest unit of data in a computer, represented by a 0 or 1.
- **Nibble:** A group of 4 bits. It can represent 16 different values (0-15).
- **Byte:** A group of 8 bits. It can represent 256 different values (0-255).

For example:
- A single bit can be 0 or 1.
- A nibble can be `1010` (which is 10 in decimal).
- A byte can be `11001010` (which is 202 in decimal).

### LSB, MSB
- **LSB (Least Significant Bit):** The bit with the lowest value in a binary number, located at the far right. It holds the least weight (2^0).
- **MSB (Most Significant Bit):** The bit with the highest value in a binary number, located at the far left. It holds the most weight (2^(n-1) for an n-bit number).

### Intel and AMD
Intel and AMD are two of the largest manufacturers of microprocessors. Both companies produce CPUs that use the x86 architecture, which is widely used in personal computers and servers. Intel processors are known for their performance in single-threaded applications, while AMD processors often offer better multi-threaded performance and value.

### Motorola Process
The Motorola 68000 series is a family of 32-bit microprocessors. It is known for its use in early Apple Macintosh computers, Amiga, and Atari ST systems. These processors use a big-endian format for storing data.

### ARM Processor
ARM (Advanced RISC Machine) processors are known for their power efficiency and are widely used in mobile devices, embedded systems, and increasingly in servers. ARM architecture supports both little-endian and big-endian formats, but little-endian is more commonly used.

## Endianness

### History
This word is derived from the word gulliver travels. In the story there was a Quarrel over the breaking of eggs via which end? the ones who broke the egg with the little end were called little endians and the one who broke ethe egg from the big end were called big endians.
![[Pasted image 20240722104227.png]] 

### Relevance to us
Now in computers whenever there is a multibyte data for example `0xa011833d1`
The question was how do we represent the data in a register?
Do we put the most significant bit first or the least significant byte first?

The most significant byte in lets say 512 is 5 which stands for the hundredth position and 2 is the least significant. In the mutlibyte data on the example above the most significant byte is `0xa011833d1`.  Humans write numbers in MSB first
##### MSB 
Most significant Byte is the one that is in the highest power for lets say in 512 it is 5 for 500 and for `0xa011833d1` it is 01
Refer [Youtube](https://www.youtube.com/watch?v=LxvFb63OOs8)

<div style="display: flex; justify-content: space-between;">
    <img src="obsidian://open?vault=TJ&file=Attachments%2FPasted%20image%2020240521173138.png" alt="Image 1" style="max-width: 45%;">
    <img src="..../Attachments/Pasted image 20240722110037.png" alt="Image 2" style="max-width: 45%;">
</div>



### Little Endian
In little-endian format, the least significant byte (LSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x78
- Address 1: 0x56
- Address 2: 0x34
- Address 3: 0x12

### Big Endian
In big-endian format, the most significant byte (MSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x12
- Address 1: 0x34
- Address 2: 0x56
- Address 3: 0x78

### Slab Servers
Slab servers refer to a modular approach to building servers, where individual components (like CPU, memory, and storage) are housed in separate "slabs" or modules. This allows for easier upgrades and maintenance, as well as better cooling and power efficiency.

### Conversion of Little Endian to Big Endian
To convert a little-endian number to big-endian, you reverse the order of the bytes. For example, to convert the 32-bit number 0x12345678 from little-endian to big-endian:

- Little-endian: 78 56 34 12
- Big-endian: 12 34 56 78

You can perform this conversion programmatically by swapping the byte positions.

## DNS Resolving
## OSI Layer

The OSI (Open Systems Interconnection) model is a conceptual framework used to understand and implement network communications. It divides the communication process into seven distinct layers, each with specific functions and protocols.

### 1. Application Layer (A)
- **Function:** Provides network services directly to end-user applications.
- **Protocols:** HTTP, FTP, SMTP, POP3, SNMP, DNS.
- **Details:** This layer interacts with software applications to implement a communicating component. It provides various services such as file transfers, email, and network data sharing.

### 2. Presentation Layer (P)
- **Function:** Translates, encrypts, and compresses data.
- **Protocols:** SSL/TLS, JPEG, MPEG.
- **Details:** The presentation layer formats or translates data for the application layer based on the syntax or semantics that the application accepts. It handles data encryption and decryption to ensure privacy and compression to reduce the amount of data that needs to be transmitted.

### 3. Session Layer (S)
- **Function:** Manages sessions between applications.
- **Protocols:** NetBIOS, RPC, SQL.
- **Details:** This layer establishes, manages, and terminates connections between applications. It controls the dialogues (connections) between computers, establishing, managing, and terminating the connections.

### 4. Transport Layer (T)
- **Function:** Ensures end-to-end communication, error checking, and data flow control.
- **Protocols:** TCP, UDP.
- **Details:** The transport layer provides reliable, transparent transfer of data between end systems. It is responsible for error detection and correction, ensuring complete data transfer. It also manages flow control to prevent network congestion.

### 5. Network Layer (N)
- **Function:** Determines the best physical path for data to travel.
- **Protocols:** IP, ICMP, IGMP.
- **Details:** The network layer controls the operation of the subnet, deciding which physical path the data should take based on network conditions, priority of service, and other factors. It routes packets from the source to the destination.

### 6. Data Link Layer (D)
- **Function:** Provides node-to-node data transfer and handles error correction from the physical layer.
- **Protocols:** Ethernet, PPP, Switches, Bridges.
- **Details:** The data link layer establishes and terminates a connection between two physically connected devices. It breaks packets into frames and transmits them, ensuring error-free data transfer. It also manages physical addressing and controls access to the physical medium.

### 7. Physical Layer (P)
- **Function:** Transmits raw bit stream over the physical medium.
- **Protocols:** Ethernet cables, USB, Bluetooth, Fiber optics.
- **Details:** The physical layer is concerned with the transmission and reception of the unstructured raw bit stream over a physical medium. It deals with the physical connection to the network and includes elements like cabling, switches, and network interface cards (NICs).

## TCP IP Layer

## References
- [Operating System Concepts by Abraham Silberschatz](https://www.wiley.com/en-us/Operating+System+Concepts%2C+10th+Edition-p-9781119456339)
- [Computer Organization and Design by David A. Patterson and John L. Hennessy](https://www.elsevier.com/books/computer-organization-and-design-arm-edition/patterson/978-0-12-801733-3)
- [ARM Architecture Reference Manual](https://developer.arm.com/documentation/ddi0100/i/)
- [Intel 64 and IA-32 Architectures Software Developer's Manual](https://software.intel.com/content/www/us/en/develop/articles/intel-sdm.html)
- [AMD Developer Guides, Manuals & ISA Documents](https://developer.amd.com/resources/developer-guides-manuals/)

**Would you like to explore specific topics in more detail or add any additional sections?**](<Here's the revised index for the lecture notes:

# Signals & Systems Lecture 3

## Index
- [Content](#content)
  - [How is File Saved in Memory Register](#how-is-file-saved-in-memory-register)
  - [Bits, Bytes, and Nibbles](#bits-bytes-and-nibbles)
  - [LSB, MSB](#lsb-msb)
  - [Intel and AMD](#intel-and-amd)
  - [Motorola Process](#motorola-process)
  - [ARM Processor](#arm-processor)
- [Endianness](#endianness)
  - [Little Endian](#little-endian)
  - [Big Endian](#big-endian)
  - [Slab Servers](#slab-servers)
  - [Conversion of Little Endian to Big Endian](#conversion-of-little-endian-to-big-endian)
- [DNS Resolving](#dns-resolving)
- [OSI Layer](#osi-layer)
  - [Application Layer](#application-layer)
  - [Presentation Layer](#presentation-layer)
  - [Session Layer](#session-layer)
  - [Transport Layer](#transport-layer)
  - [Network Layer](#network-layer)
  - [Data Link Layer](#data-link-layer)
  - [Physical Layer](#physical-layer)
- [TCP/IP Layer](#tcp-ip-layer)
- [References](#references)

## Content

### How is File Saved in Memory Register
Files are saved in memory registers as a series of bytes. The operating system and file system manage how these bytes are allocated in memory. The data is stored in binary format, with each byte consisting of 8 bits. The sequence and structure of these bytes depend on the file format and the architecture of the system (such as little-endian or big-endian).

### Bits, Bytes, and Nibbles
- **Bit:** The smallest unit of data in a computer, represented by a 0 or 1.
- **Nibble:** A group of 4 bits. It can represent 16 different values (0-15).
- **Byte:** A group of 8 bits. It can represent 256 different values (0-255).

For example:
- A single bit can be 0 or 1.
- A nibble can be `1010` (which is 10 in decimal).
- A byte can be `11001010` (which is 202 in decimal).

### LSB, MSB
- **LSB (Least Significant Bit):** The bit with the lowest value in a binary number, located at the far right. It holds the least weight (2^0).
- **MSB (Most Significant Bit):** The bit with the highest value in a binary number, located at the far left. It holds the most weight (2^(n-1) for an n-bit number).

### Intel and AMD
Intel and AMD are two of the largest manufacturers of microprocessors. Both companies produce CPUs that use the x86 architecture, which is widely used in personal computers and servers. Intel processors are known for their performance in single-threaded applications, while AMD processors often offer better multi-threaded performance and value.

### Motorola Process
The Motorola 68000 series is a family of 32-bit microprocessors. It is known for its use in early Apple Macintosh computers, Amiga, and Atari ST systems. These processors use a big-endian format for storing data.

### ARM Processor
ARM (Advanced RISC Machine) processors are known for their power efficiency and are widely used in mobile devices, embedded systems, and increasingly in servers. ARM architecture supports both little-endian and big-endian formats, but little-endian is more commonly used.

## Endianness

### History
This word is derived from the word gulliver travels. In the story there was a Quarrel over the breaking of eggs via which end? the ones who broke the egg with the little end were called little endians and the one who broke the egg from the big end were called big endians.
![[Pasted image 20240722104227.png]] 

### Relevance to Us
Now in computers whenever there is a multibyte data for example `0xa011833d1`
The question was how do we represent the data in a register?
Do we put the most significant bit first or the least significant byte first?
Refer [Youtube](https://www.youtube.com/watch?v=LxvFb63OOs8)

### Little Endian
In little-endian format, the least significant byte (LSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x78
- Address 1: 0x56
- Address 2: 0x34
- Address 3: 0x12

### Big Endian
In big-endian format, the most significant byte (MSB) is stored first, at the lowest memory address. For example, the 32-bit hexadecimal number 0x12345678 would be stored as:
- Address 0: 0x12
- Address 1: 0x34
- Address 2: 0x56
- Address 3: 0x78

### Slab Servers
Slab servers refer to a modular approach to building servers, where individual components (like CPU, memory, and storage) are housed in separate "slabs" or modules. This allows for easier upgrades and maintenance, as well as better cooling and power efficiency.

### Conversion of Little Endian to Big Endian
To convert a little-endian number to big-endian, you reverse the order of the bytes. For example, to convert the 32-bit number 0x12345678 from little-endian to big-endian:

- Little-endian: 78 56 34 12
- Big-endian: 12 34 56 78

You can perform this conversion programmatically by swapping the byte positions.

## DNS Resolving

## OSI Layer

The OSI (Open Systems Interconnection) model is a conceptual framework used to understand and implement network communications. It divides the communication process into seven distinct layers, each with specific functions and protocols.

### 1. Application Layer (A)
- **Function:** Provides network services directly to end-user applications.
- **Protocols:** HTTP, FTP, SMTP, POP3, SNMP, DNS.
- **Details:** This layer interacts with software applications to implement a communicating component. It provides various services such as file transfers, email, and network data sharing.

### 2. Presentation Layer (P)
- **Function:** Translates, encrypts, and compresses data.
- **Protocols:** SSL/TLS, JPEG, MPEG.
- **Details:** The presentation layer formats or translates data for the application layer based on the syntax or semantics that the application accepts. It handles data encryption and decryption to ensure privacy and compression to reduce the amount of data that needs to be transmitted.

### 3. Session Layer (S)
- **Function:** Manages sessions between applications.
- **Protocols:** NetBIOS, RPC, SQL.
- **Details:** This layer establishes, manages, and terminates connections between applications. It controls the dialogues (connections) between computers, establishing, managing, and terminating the connections.

### 4. Transport Layer (T)
- **Function:** Ensures end-to-end communication, error checking, and data flow control.
- **Protocols:** TCP, UDP.
- **Details:** The transport layer provides reliable, transparent transfer of data between end systems. It is responsible for error detection and correction, ensuring complete data transfer. It also manages flow control to prevent network congestion.

### 5. Network Layer (N)
- **Function:** Determines the best physical path for data to travel.
- **Protocols:** IP, ICMP, IGMP.
- **Details:** The network layer controls the operation of the subnet, deciding which physical path the data should take based on network conditions, priority of service, and other factors. It routes packets from the source to the destination.

### 6. Data Link Layer (D)
- **Function:** Provides node-to-node data transfer and handles error correction from the physical layer.
- **Protocols:** Ethernet, PPP, Switches, Bridges.
- **Details:** The data link layer establishes and terminates a connection between two physically connected devices. It breaks packets into frames and transmits them, ensuring error-free data transfer. It also manages physical addressing and controls access to the physical medium.

### 7. Physical Layer (P)
- **Function:** Transmits raw bit stream over the physical medium.
- **Protocols:** Ethernet cables, USB, Bluetooth, Fiber optics.
- **Details:** The physical layer is concerned with the transmission and reception of the unstructured raw bit stream over a physical medium. It deals with the physical connection to the network and includes elements like cabling, switches, and network interface cards (NICs).

## TCP/IP Layer

## References
- [Operating System Concepts by Abraham Silberschatz](https://www.wiley.com/en-us/Operating+System+Concepts%2C+10th+Edition-p-9781119456339)
- [Computer Organization and Design by David A. Patterson and John L. Hennessy](https://www.elsevier.com/books/computer-organization-and-design-arm-edition/patterson/978-0-12-801733-3)
- [ARM Architecture Reference Manual](https://developer.arm.com/documentation/ddi0100/i/)
- [Intel 64 and IA-32 Architectures Software Developer's Manual](https://software.intel.com/content/www/us/en/develop/articles/intel-sdm.html)
- [AMD Developer Guides, Manuals &

 ISA Documents](https://developer.amd.com/resources/developer-guides-manuals/)
- [IEEE Xplore Digital Library](https://ieeexplore.ieee.org/)
- [RFC 791: Internet Protocol](https://tools.ietf.org/html/rfc791)

