# SSH-Template
Connect to network equipment using paramiko module.

NOTES:
Paramiko module collects all output in buffer.	When a recv method is called (connection.recv(65535)),	paramiko	returns all	the contents of the buffer.	After running recv, the buffer is empty. Therefore if you only need to get the output of a specific command, you need to call recv, but do not make the print.

  ssh.send('enable\n')				
ssh.send(ENABLE_PASS	+	'\n')				
time.sleep(1)
ssh.send('terminal	length	0\n')	
time.sleep(1)				
#Тут	мы	вызываем	recv,	но	не	выводим	содержимое	буфера				
ssh.recv(1000)
ssh.send(COMMAND	+	'\n')				
time.sleep(3)				
result	=	ssh.recv(5000).decode('utf-8')				
print(result)
