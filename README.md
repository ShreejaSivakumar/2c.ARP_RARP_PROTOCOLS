# 2c.SIMULATING ARP /RARP PROTOCOLS

# EX.NO : 2C
# DATE : 22/05/26
# NAME : SHREEJA R S
# REF.NO : 25017561

## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
SERVER :- 
```
import socket

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(5)

c, addr = s.accept()

address = {
    "165.165.80.80": "6A:08:AA:C2",
    "165.165.79.1": "8A:BC:E3:FA"
}

while True:
    ip = c.recv(1024).decode()

    try:
        c.send(address[ip].encode())

    except KeyError:
        c.send("Not Found".encode())
```
CLIENT :-
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    ip = input("Enter logical Address : ")

    s.send(ip.encode())

    print("MAC Address", s.recv(1024).decode())
```


## OUTPUT - ARP

<img width="1701" height="804" alt="Screenshot 2026-05-22 143604" src="https://github.com/user-attachments/assets/e99c19c4-886c-454a-970a-339d6bba9aa4" />


## PROGRAM - RARP

SERVER :- 
```
import socket

s = socket.socket()

s.bind(('localhost', 9000))

s.listen(5)

c, addr = s.accept()

address = {
    "6A:08:AA:C2": "192.168.1.100",
    "8A:BC:E3:FA": "192.168.1.99"
}

while True:
    ip = c.recv(1024).decode()

    try:
        c.send(address[ip].encode())

    except KeyError:
        c.send("Not Found".encode())
```
CLIENT :-
```
import socket

s = socket.socket()

s.connect(('localhost', 9000))

while True:
    ip = input("Enter MAC Address : ")

    s.send(ip.encode())

    print("Logical Address", s.recv(1024).decode())
```


## OUTPUT -RARP

<img width="1700" height="866" alt="Screenshot 2026-05-22 144057" src="https://github.com/user-attachments/assets/7b447331-fb97-491b-ac04-ade23a7c9370" />


## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.



















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.





















































.
.
.
.

.
.
.


