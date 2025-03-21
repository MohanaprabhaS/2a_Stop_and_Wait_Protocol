# 2a_Stop_and_Wait_Protocol
# DEVELOPED BY: MOHANAPRABHA S
# REGISTER NO:212224040197
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
```
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

```

## OUTPUT

![Screenshot 2025-03-20 112838](https://github.com/user-attachments/assets/1f8253c9-fdad-4379-9fa7-ebde6a0f8fc1)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
