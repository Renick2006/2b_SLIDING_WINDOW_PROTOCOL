# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: RENICK FABIAN RAJESH
## REG NO: 212224230227
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```
## OUPUT
![Screenshot 2025-03-19 111737](https://github.com/user-attachments/assets/5fdf7e37-3fb4-42e7-900f-af0342eb01af)
![Screenshot 2025-03-19 111753](https://github.com/user-attachments/assets/bbbf06b7-bda9-4cc3-85ea-94c44ebbff6d)
![Screenshot 2025-03-19 111349](https://github.com/user-attachments/assets/12581ca3-e6d7-4b59-94b3-e291dcf230e4)
![Screenshot 2025-03-19 111414](https://github.com/user-attachments/assets/7b9e7ba2-fe0a-4bc7-81e8-d9efa45dcd55)




## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
