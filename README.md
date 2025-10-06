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
s.bind(('localhost',800)) 
s.listen(5) 
c,addr=s.accept() 
size=int(input("Enter number of frames to send : ")) 
l=list(range(size)) 
s=int(input("Enter Window Size : ")) 
st=0 
i=0 
while True: 
    while(i<len(l)): 
            st+=s 
            c.send(str(l[i:st]).encode()) 
            ack=c.recv(1024).decode() 
            if ack: 
                print(ack) 
                i+=s
```
### CLIENT
```
import socket 
s=socket.socket() 
s.connect(('localhost',8001))
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode()) 
```   
## OUPUT

### server

<img width="470" height="244" alt="Screenshot 2025-10-06 232940" src="https://github.com/user-attachments/assets/b9e14ec4-c673-46e6-ba5d-e8c8dafe89b8" />

### client


<img width="474" height="182" alt="Screenshot 2025-10-06 232948" src="https://github.com/user-attachments/assets/1096d05e-c400-4990-847a-e43b4816e928" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
