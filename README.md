# 2a_Stop_and_Wait_Protocol
# DEVELOPED BY: MOHANAPRABHA S
REGISTER NO:212224040197
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
Client

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break

Server 

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())


## OUTPUT
![Screenshot 2025-03-20 103310](https://github.com/user-attachments/assets/f99d3c06-9e5b-45d1-b9d9-73256f7681d3)

![Screenshot 2025-03-20 103258](https://github.com/user-attachments/assets/4d7139cf-3705-4f48-a0c5-744151cffa42)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
