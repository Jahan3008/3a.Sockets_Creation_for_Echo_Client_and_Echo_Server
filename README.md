# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
Name:JAHAN J
Reg No:212224220040
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
Client:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```
Server:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
## OUTPUT
Client:
![image](https://github.com/user-attachments/assets/a3b601c5-5c56-4618-8de3-4c44e41e4b23)



Server:
![image](https://github.com/user-attachments/assets/102d2612-7d86-4e37-bd28-e5a62b1b25c8)



## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
