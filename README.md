# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
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
server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 12345))
s.listen(1)

print("Server waiting...")
c, addr = s.accept()
print("Client connected")

while True:
    msg = c.recv(1024).decode()

    if msg == "exit":
        break

    print("Client:", msg)
    c.send(msg.encode())

c.close()
s.close()

```
client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 12345))

while True:
    msg = input("Enter message: ")
    s.send(msg.encode())

    if msg == "exit":
        break

    data = s.recv(1024).decode()
    print("Echo:", data)

s.close()

```

## OUPUT
<img width="580" height="180" alt="image" src="https://github.com/user-attachments/assets/f0f1d737-fe6e-414d-bb5d-5bf861f8e255" />
<img width="546" height="210" alt="image" src="https://github.com/user-attachments/assets/69aa7368-2ac7-44eb-aa47-8f987db4335f" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
