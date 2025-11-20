# 2a_Stop_and_Wait_Protocol
# Name: Abhishek kannan M
# Reg no: 212224040007
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## Server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))   
s.listen(5)
c, addr = s.accept()
print("Connected with", addr)

while True:
    i = input("Enter data: ")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print("Server received:", ack)
    else:
        c.close()
        break
```

## Cilent.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))   
while True:
    data = s.recv(1024).decode()
    if not data:
        break
    print("Client received:", data)
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="1503" height="893" alt="image" src="https://github.com/user-attachments/assets/4ade9cff-c00d-4540-9d12-265790c6031c" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
