# 2a_Stop_and_Wait_Protocol
### NAME : VINOTH M P
### REG NO : 212223240182
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
Client Side:

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
```
Server Side:

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recived".encode())
```

## OUTPUT
![image](https://github.com/user-attachments/assets/abc5a201-277c-4cd2-a207-28c64a922c28)
![image](https://github.com/user-attachments/assets/1a8f9e01-c12e-4e90-9f88-9fcdc9a60781)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
