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
## client

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

## server

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```


## OUTPUT
![Screenshot 2024-08-27 085130](https://github.com/user-attachments/assets/3a4f1081-fccb-4507-a44a-cd069db6d07f)

![Screenshot 2024-08-27 085153](https://github.com/user-attachments/assets/1617f930-0802-4ac2-8bbd-054e6c7c1cd5)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
