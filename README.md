# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name: T.Manikandan
## Register number: 212224110037
## AIM
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## server
```python
import socket
s = socket.socket()
s.bind(('localhost', 9999))
s.listen(1)
print("Server listening...")
conn, addr = s.accept()
print(f"Connected to {addr}")

while True:
    frames = conn.recv(1024).decode()
    if not frames:
        break

    print(f"Received frames: {frames}")
    ack_message = f"ACK for frames: {frames}"
    conn.send(ack_message.encode())

conn.close()  
s.close()
```
## client
```python
import socket
s = socket.socket()
s.bind(('localhost', 9999))
s.listen(1)
print("Server listening...")
conn, addr = s.accept()
print(f"Connected to {addr}")

while True:
    frames = conn.recv(1024).decode()
    if not frames:
        break

    print(f"Received frames: {frames}")
    ack_message = f"ACK for frames: {frames}"
    conn.send(ack_message.encode())

conn.close()  
s.close()
```
## OUTPUT
<img width="842" height="193" alt="image" src="https://github.com/user-attachments/assets/0feb3885-e66c-4aea-bacd-2c3ca48cca0c" />

<img width="857" height="260" alt="image" src="https://github.com/user-attachments/assets/f41c5448-de86-4d69-98f9-16afcf0c4474" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
