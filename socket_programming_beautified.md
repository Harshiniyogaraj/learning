# 🧩 Socket Programming in C

---

## 🔌 What is a Socket?

A **socket** is used to create a connection between a **client** and a **server**, allowing them to communicate with each other.

- **Client:** Connects to the server through sockets.  
- **Server:** Waits for clients to connect and communicate through sockets.

---

## 💬 What is Socket Programming?

**Socket programming** is the process of connecting two programs — a **client** and a **server** — so that they can **exchange data** with each other over a network.

---

## ⚙️ Functions Used in Socket Programming

The main functions are:

```
socket()
bind()
listen()
connect()
accept()
send() / recv() / read() / write() / sendto() / recvfrom()
close()
```

---

## 👨‍💻 Client Functions

| Function | Purpose |
|-----------|----------|
| **socket()** | Creates a new socket for connection |
| **connect()** | Connects to the server |
| **send()/write()** | Sends data through the socket (client → server) |
| **recv()/read()** | Receives data through the socket (server → client) |
| **close()** | Terminates the socket |

---

## 🖥️ Server Functions

| Function | Purpose |
|-----------|----------|
| **socket()** | Creates socket for connection |
| **bind()** | Assigns IP address with specific port and service |
| **listen()** | Waits for incoming connections from clients |
| **accept()** | Accepts incoming client connection |
| **send()/write()** | Sends data through the socket |
| **recv()/read()** | Receives data through the socket |
| **close()** | Terminates the socket |

---

## 🧠 Syntax and Descriptions

### 🧱 `socket()` — Create a Connection Endpoint

**Purpose:** Creates a socket.  
**Syntax:**  
```c
int socket(int family, int type, int protocol);
```

| Parameter | Description |
|------------|--------------|
| **family** | Address family — `AF_INET` (IPv4), `AF_INET6` (IPv6) |
| **type** | Socket type — `SOCK_STREAM` (Stream Socket), `SOCK_DGRAM` (Datagram Socket) |
| **protocol** | Protocol — `IPPROTO_TCP` (TCP), `IPPROTO_UDP` (UDP) |

**Example:**  
```c
int sock = socket(AF_INET, SOCK_STREAM, 0);
```
Here, `0` is the default protocol. If `SOCK_STREAM` is used, the default protocol is **TCP**. For `SOCK_DGRAM`, the default is **UDP**.

---

### 📍 `bind()` — Attach an IP Address and Port

**Purpose:** Assigns IP address with a specific port and service.  
**Syntax:**  
```c
int bind(int sockfd, struct sockaddr *serv_addr, int addrlen);
```

| Parameter | Description |
|------------|-------------|
| **sockfd** | Socket descriptor |
| **serv_addr** | Structure containing server IP address and port |
| **addrlen** | Length of address in bytes |

**Example:**  
```c
struct sockaddr_in serv_addr;
serv_addr.sin_family = AF_INET;        // Address family
serv_addr.sin_port = htons(port_num);  // Port number
serv_addr.sin_addr.s_addr = INADDR_ANY; // Listen to all interfaces

int bind(sockfd, (struct sockaddr*)&serv_addr, sizeof(serv_addr));
```

---

### 🔗 `connect()` — Connect to Server

**Purpose:** Connects to the server’s port.  
**Syntax:**  
```c
int connect(int sockfd, struct sockaddr *serv_addr, int addrlen);
```

**Example:**  
```c
int connect(sockfd, (struct sockaddr*)&serv_addr, sizeof(serv_addr));
```

---

### 🕓 `listen()` — Wait for Client Connections

**Purpose:** Makes the socket ready to accept incoming connections.  
**Syntax:**  
```c
int listen(int sockfd, int backlog);
```
| Parameter | Description |
|------------|-------------|
| **sockfd** | Socket descriptor |
| **backlog** | Maximum number of pending connections |

**Example:**  
```c
int listen(sockfd, 15); // Allows up to 15 pending connections
```

---

### ✅ `accept()` — Accept Client Connection

**Syntax:**  
```c
int accept(int sockfd, struct sockaddr *cli_addr, int addrlen);
```

| Parameter | Description |
|------------|-------------|
| **sockfd** | Socket descriptor |
| **cli_addr** | Holds client info |
| **addrlen** | Size of client address |

**Example:**  
```c
struct sockaddr_in cli_addr;
int accept(sockfd, (struct sockaddr*)&cli_addr, sizeof(cli_addr));
```

---

### 📡 `send()` / `recv()` — Data Transmission

**Purpose:** Used by TCP to send and receive data (stream socket).  
**Syntax:**  
```c
int send(int sockfd, void *msg, int len, int flags);
int recv(int sockfd, void *msg, int len, int flags);
```

| Parameter | Description |
|------------|-------------|
| **sockfd** | Socket descriptor |
| **msg** | Message buffer (data to send or receive) |
| **len** | Length of message |
| **flags** | Usually set to 0 |

**Example:**  
```c
char send_msg[1000], recv_msg[2000];
int send_bytes, recv_bytes;

send_bytes = send(sockfd, send_msg, 1000, 0);
recv_bytes = recv(sockfd, recv_msg, 2000, 0);
```

---

### 📴 `close()` — Terminate the Socket

**Purpose:** Closes the connection and frees resources.  
**Syntax:**  
```c
int close(int sockfd);
```

---

> 💡 **Summary:** Socket programming is essential for enabling real-time communication between distributed systems. It forms the foundation of web servers, chat apps, and networked games.

---
