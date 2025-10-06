# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name : Reena K
## Register No : 212224040272
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### SERVER
```
import socket 
s=socket.socket() 
s.bind(('localhost',8080))

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
### CLIENT
```
import socket 
s=socket.socket() 
s.connect(('localhost',8080)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```   
## OUPUT

### server

<img width="589" height="191" alt="Screenshot 2025-10-06 161840" src="https://github.com/user-attachments/assets/90bc1a9d-c5b5-4960-9856-6628bda3dd9a" />


### client


<img width="660" height="316" alt="Screenshot 2025-10-06 161829" src="https://github.com/user-attachments/assets/749f65a9-fed9-4a75-ade1-e990a0623e7b" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
