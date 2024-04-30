# Ethical-Hacking-Techniques---19CS417-
Ethical Hacking Techniques - 19CS417 
```
BHARGAVA s
212221040029
CSE (III)
```
# Simple echo server and client using Python socket
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
### SERVER CODE
```
#echo-server.py
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
### CLIENT CODE
```
# echo-client.py
import socket
HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```
## OUTPUT:
### SERVER OUTPUT
![image](https://github.com/Bhargava-123/Ethicka-Hacking-Techniques---19CS417-/assets/85554376/9c9d41d2-df56-4f78-aab5-fa312036beab)

### CLIENT OUTPUT
![image](https://github.com/Bhargava-123/Ethicka-Hacking-Techniques---19CS417-/assets/85554376/c7647b26-f8c3-4b0f-81fb-c3420851a984)


## RESULT:
The program is executed successfully
