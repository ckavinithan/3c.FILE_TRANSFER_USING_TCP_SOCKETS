# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
Developed By : Kavinithan.C

Register Number : 212225230134

## Server Program

```
import socket 
# Create socket 
server = socket.socket() 
# Bind IP and port 
server.bind(("127.0.0.1", 5555)) 
# Listen for client 
server.listen(1) 
print("Server waiting for connection...") 
# Accept client 
client, addr = server.accept() 
print("Connected to:", addr) 
# Ask filename 
filename = input("Enter file name to send: ") 
# Open and send file 
with open(filename, "rb") as file: 
    data = file.read() 
    client.send(data) 
print("File sent successfully") 
# Close connections 
client.close() 
server.close()
```

## Client
```
import socket 
# Create socket 
client = socket.socket() 
# Connect to server 
client.connect(("127.0.0.1", 5555)) 
# Save file name 
save_name = input("Enter name to save file: ") 
# Receive data 
data = client.recv(1000000) 
# Save file 
with open(save_name, "wb") as file: 
    file.write(data) 
print("File received successfully") 
# Close connection 
client.close() 

```
## OUTPUT

## Sample.txt

<img width="1920" height="1080" alt="Screenshot 2026-05-20 113630" src="https://github.com/user-attachments/assets/56c938bc-d582-442f-a3de-2915cae28b73" />

## Server 

<img width="1920" height="1080" alt="Screenshot 2026-05-20 113604" src="https://github.com/user-attachments/assets/c82a0776-28a6-4958-95f4-1b6a83777847" />

## Client

<img width="1920" height="1080" alt="Screenshot 2026-05-20 113615" src="https://github.com/user-attachments/assets/d51e982d-a638-469f-ae70-d66e8e950e5e" />

## Recieved.txt

<img width="1920" height="1080" alt="Screenshot 2026-05-20 113643" src="https://github.com/user-attachments/assets/03eccf12-c73f-49b3-9740-b559b157b4be" />



## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
