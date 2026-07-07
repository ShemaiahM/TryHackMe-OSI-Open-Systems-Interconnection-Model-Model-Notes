# TryHackMe-OSI-Open-Systems-Interconnection-Model-Model-Notes


| Layer | Name | Core Job | Key Tech/Concept |
| :--- | :--- | :--- | :--- |
| **7** | **Application** | User interaction | HTTP, DNS, SMTP |
| **6** | **Presentation** | Format & Encryption | SSL/TLS, JPEG, ZIP |
| **5** | **Session** | Dialogue control | Establishing/Ending sessions |
| **4** | **Transport** | End-to-end delivery | TCP (Reliable), UDP (Fast) |
| **3** | **Network** | Logical Routing | IP Addresses, Routers |
| **2** | **Data Link** | Physical Addressing | MAC Addresses, NICs, Frames |
| **1** | **Physical** | Raw Bits | Cables, Electricity, Hubs |

# OSI Model (Open Systems Interconnection Model)

**The Fundamental Networking Framework:** The stages of how data is moved across a network.

---

### 1. Physical
The Hardware and Cables. Ethernet Cable(s). Devices use electrical signals to transfer data between themselves in a binary numbering system (1 & 0).

### 2. Data Link
The Physical addressing of a transmission. Every Networking device comes with a NIC (network Interface Card). The NIC comes with a unique MAC (Media Access Control) address to identify it (they can’t be changed but, they can be spoofed).  When data is sent across a network, the physical address is used to identify where the data is to be sent.

### 3. Network Layer
The OSI Layer that’s routing and reassembling of data over a network. Routing determines the optimal path for data (data broken down into chunks aka packets) to travel. Protocols like OSPF (Open Shortest Path First) & RIP (Routing Information Protocol). Essentially what is the shortest, fastest & reliable path, for packets(data) to travel? At this level Devices like Routers are known as layer 3 devices because they are capable of delivering packets and everything is dealt with via IP Addresses not Mac.

### 4. Transport
Transportation of data across a network. Two different protocols are used based on numerous factors. TCP (Transmission Control Protocol) & UDP (User Datagram Protocol). Segments (TCP) or Datagrams (UDP).

#### Transmission Control Protocol
Designed to be reliable and guaranteed that data will be received. TCP has constant connection between two devices for the data to be sent & received. TCP has Error Checking, this is the guarantee, where data will be sent and received & reassembled in the same order. TCP used for emails & file sharing.

| Advantages | Disadvantages |
| :--- | :--- |
| Guarantees accuracy of data | Needs Constant reliable connection between devices. If a tiny chunk of data missing then entire chunk of data cant be used. |
| Does a lot more processes for reliability | TCP slower than UDP, because of the process of reliability |

#### User Datagram Protocol
Not as thorough as TCP, no reliability or error checking. Data get sent to device whether it gets there or not. There’s no synchronisation of devices like TCP. UDP useful for streaming and for sharing small pieces of data.

| Advantages | Disadvantages |
| :--- | :--- |
| UDP faster than TCP. | No guarantee or reliability that data will be received. |
| | There’s no continuous connection like TCP, so all the data doesn’t get sent. |
| | Unstable connections give terrible experience for user. |

### 5. Session
This layer manages the dialogue between two computers. It maintains a connection to a device where the data is being sent. When connection is recognised & active, then the session is created. If connection is lost or not in use, the session will close. Sessions are unique, data can’t travel over different sessions yet, only across each session instead. It is responsible for establishing, managing, and terminating connections (sessions).

### 6. Presentation
Making sure data sent to one computer is understood by another. This translates data into a neutral format so any system can understand like Outlook & Gmail, they may store data differently, yet presentation layer ensures that it looks the same on the recipients’ screen as it did mine. This layer formats & encodes data into standardised formats. There is also Encryption & decryption, data scrambled during transportation & then decrypted when it arrives. HTTPS, which uses this layer to ensure your data stays private while it travels. It also handles Compression (e.g., JPEG, ZIP) to make data smaller before it travels.

### 7. Application
Application Layer where protocols and rules are determined, so can users interact with sent & or received data. It is the set of protocols that the application uses to communicate (e.g., HTTP, HTTPS, SMTP, FTP).
