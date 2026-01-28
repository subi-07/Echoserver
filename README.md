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
Server code


# echo-server.py


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

Client Code:
# echo-client.py


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")

## OUTPUT:

![WhatsApp Image 2026-01-28 at 1 10 24 PM](https://github.com/user-attachments/assets/47989b48-75c8-454a-98c1-4714f92cf8a9)


![WhatsApp Image 2026-01-28 at 10 21 48 AM](https://github.com/user-attachments/assets/c5216022-4758-4e87-ba91-11c72b72b00e)


![WhatsApp Image 2026-01-28 at 10 22 49 AM](https://github.com/user-attachments/assets/189c3239-8c5f-48f6-9c3c-5d3a09e76c8c)


![WhatsApp Image 2026-01-28 at 10 22 50 AM](https://github.com/user-attachments/assets/5a2ed793-1b50-49b5-8e50-9dd173d5250f)


## RESULT:
The program is executed successfully
