# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM:
echoserver
```
import socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))
server_socket.listen(1)

print("Echo Server is waiting for connection...")
client_socket, addr = server_socket.accept()
print("Connected to:", addr)
while True:
    data = client_socket.recv(1024).decode()
    if not data:
        break
    print("Client:", data)
    client_socket.send(data.encode())
client_socket.close()
server_socket.close()
```
echoclient
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
client_socket.connect((host, port))
while True:
    message = input("Enter message: ")
    if message.lower() == 'exit':
        break
    client_socket.send(message.encode())
    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)
client_socket.close()
```
## OUPUT:
<img width="1115" height="561" alt="Screenshot 2026-11-18 102308" src="https://github.com/user-attachments/assets/d503b56c-12ae-433d-ad4b-fa2a2f7ecae6" />
<img width="1107" height="502" alt="Screenshot 2026-11-18 102316" src="https://github.com/user-attachments/assets/d831b5e9-3521-4a90-9b5b-d00d7fd1c459" />

## RESULT:
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
