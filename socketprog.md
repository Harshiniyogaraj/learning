
# Socket and Socket Programming

## What is a Socket?

A **socket** is used to create a connection between a client and a server so that they can communicate with each other.

- **Client:** Connects to the server through sockets.  
- **Server:** Waits for clients to connect and responds to their requests via sockets.

---

## What is Socket Programming?

**Socket programming** is the process of connecting two programs (client and server) to communicate with each other.

---

## Functions Used in Socket Programming

The main functions are:

- `socket()`
- `bind()`
- `listen()`
- `connect()`
- `accept()`
- `send() / recv() / read() / write() / sendto() / recvfrom()`
- `close()`

---

## Functions of Client

- **`socket()`**: Creates a new socket for connection.  
- **`connect()`**: Connects to the server.  
- **`send() / write()`**: Sends data through the socket.  
- **`recv() / read()`**: Receives data through the socket.  
- **`close()`**: Terminates the socket connection.

---

## Functions of Server

- **`socket()`**: Creates a socket to accept client connections.  
- **`bind()`**: Assigns an IP address with a specific port and service.  
- **`listen()`**: Waits for incoming connections from clients.  
- **`accept()`**: Accepts incoming client connections.  
- **`send() / write()`**: Sends data to the client.  
- **`recv() / read()`**: Receives data from the client.  
- **`close()`**: Terminates the socket connection.

---

## Syntax of Functions

### `socket()`

**Purpose:** Creates a socket.  

```c
int socket(int family, int type, int protocol);
````

| Family   | Description |
| -------- | ----------- |
| AF_INET  | IPv4        |
| AF_INET6 | IPv6        |

| Type        | Description     |
| ----------- | --------------- |
| SOCK_STREAM | Stream Socket   |
| SOCK_DGRAM  | Datagram Socket |

| Protocol    | Description  |
| ----------- | ------------ |
| IPPROTO_TCP | TCP Protocol |
| IPPROTO_UDP | UDP Protocol |

**Example:**

```c
int sockfd = socket(AF_INET, SOCK_STREAM, 0); // 0 is default protocol
```

> Note: Default protocol is TCP for `SOCK_STREAM` and UDP for `SOCK_DGRAM`.

---

### `bind()`

**Purpose:** Attaches an IP address and port to a socket.

```c
int bind(int sockfd, struct sockaddr *serv_addr, int addrlen);
```

**Example:**

```c
struct sockaddr_in serv_addr;
serv_addr.sin_family = AF_INET;            // Address family
serv_addr.sin_port = htons(PORT);          // Port number
serv_addr.sin_addr.s_addr = INADDR_ANY;    // Listen on all interfaces

int result = bind(sockfd, (struct sockaddr*)&serv_addr, sizeof(serv_addr));
```

---

### `connect()`

**Purpose:** Connects a client socket to a server.

```c
int connect(int sockfd, struct sockaddr *serv_addr, int addrlen);
```

**Example:**

```c
int result = connect(sockfd, (struct sockaddr*)&serv_addr, sizeof(serv_addr));
```

---

### `listen()`

**Purpose:** Waits for incoming client connections.

```c
int listen(int sockfd, int backlog);
```

* `backlog`: Maximum number of pending connections.

**Example:**

```c
listen(sockfd, 15); // Allows up to 15 pending connections
```

---

### `accept()`

**Purpose:** Accepts an incoming client connection.

```c
int accept(int sockfd, struct sockaddr *cli_addr, int *addrlen);
```

**Example:**

```c
struct sockaddr_in cli_addr;
int new_sock = accept(sockfd, (struct sockaddr*)&cli_addr, sizeof(cli_addr));
```

---

### `send()` / `recv()`

**Purpose:** Used by TCP sockets to send and receive data.

```c
int send(int sockfd, void *msg, int len, int flags);
int recv(int sockfd, void *msg, int len, int flags);
```

* `sockfd` : Socket descriptor
* `msg` : Data to send or receive
* `len` : Length of data
* `flags` : Usually `0`

**Example:**

```c
char send_msg[1000], recv_msg[2000];
int send_bytes, recv_bytes;

send_bytes = send(sockfd, send_msg, 1000, 0);
recv_bytes = recv(sockfd, recv_msg, 2000, 0);
```

---

### `close()`

**Purpose:** Terminates a socket connection.

```c
close(sockfd);
```

---


