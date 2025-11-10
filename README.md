# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
SERVER
     
     import socket
     s = socket.socket()
     s.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)  # Allow address reuse
     s.bind(('localhost', 8090))
     s.listen(5)
     print("Server is listening...")
     c, addr = s.accept()
     print("Connection from:", addr)
     while True:
         ClientMessage = c.recv(1024).decode()
         print("Client >", ClientMessage)
         msg = input("Server > ")
         c.send(msg.encode())

CLIENT

     import socket
     s = socket.socket()
     s.connect(('localhost', 8090))
     while True:
         msg = input("Client > ")
         s.send(msg.encode())
         print("Server >", s.recv(1024).decode())

##OUTPUT
SERVER:
<img width="693" height="285" alt="image" src="https://github.com/user-attachments/assets/a2104b18-9250-47c4-81a9-049113112238" />

CLIENT:
<img width="579" height="309" alt="image" src="https://github.com/user-attachments/assets/edf3312f-de33-44ca-aae6-f6c5672398e2" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
