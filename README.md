# 2a_Stop_and_Wait_Protocol
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
## Client

```
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
```
## Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
 ```   
## OUTPUT
## Client 

![361639442-3d9c27ef-7cac-4e08-9450-09022c8718ee](https://github.com/user-attachments/assets/ac9a8071-78d8-4950-aea0-e0d86a376e5e)

## Server

![361639967-78dcca97-def0-4d62-b970-4737bf68721c](https://github.com/user-attachments/assets/c553cbd2-c938-4621-9bc1-8ded7df32512)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
