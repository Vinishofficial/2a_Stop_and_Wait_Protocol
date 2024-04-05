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

## Program :
  ## Client :
  ```
  import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter the data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close
        break
  ```
  ## Server :
   ```
   import socket
  s=socket.socket()
  s.connect(('localhost',8000))
  while True:
      print(s.recv(1024).decode())
      s.send("Acknowledgement Received".encode())
   ```
## Output :
  ## Client :
  ![image](https://github.com/Vinishofficial/SocketStudy/assets/146931793/c61548a3-524b-4eb4-9759-484fe37e53bf)
  ## Server :
  ![image](https://github.com/Vinishofficial/SocketStudy/assets/146931793/2d5a89d8-35f3-4773-9934-01f08dc46ed3)
  
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
