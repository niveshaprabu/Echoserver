# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
## SERVER:
```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## CLIENT:
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"PAVITHRA R-212222230106")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT:
## SERVER:
![Screenshot 2024-09-24 233434](https://github.com/user-attachments/assets/ae3db304-6c32-45e7-a806-3bc661002125)

## CLIENT:
![Screenshot 2024-09-24 233711](https://github.com/user-attachments/assets/c57c8dde-6d28-4011-8dc4-686379dd71b9)

## RESULT:
The program is executed successfully
