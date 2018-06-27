# SSH-Template
Connect to network equipment using paramiko module.

NOTES:
Paramiko module collects all output in buffer.	When a recv method is called (connection.recv(65535)),	paramiko	returns all	the contents of the buffer.	After running recv, the buffer is empty. Therefore if you only need to get the output of a specific command, you need to call recv, but do not make the print.
