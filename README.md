# Project 2

## My Approach:
- First, I implemented the command line parser and made sure that I got the correct values for each parameter after parsing. Challenge was to differentiate between two cases of cp and mv commands. (local path followed by remote path or remote path followed by local path)
- Next, I added support for conenction establishment and verbose mode. With the usage of verbose mode, I confirmed that I can establish connections correctly.
- Next, I added support for passive mode and data channels to implement ls operation. The reason I implemented the ls operation first was to be able to observe the effects of other operations.
- Next, I implemented rm, rmdir, and mkdir operations. I confirmed they worked correctly using ls operation.
- Finally, I implemented cp and then mv. 

## Challenges I Faced:
When I tried uploading files to the server, I got the error 426 and observed that the files I sent got corrupted on their way to the server. The solution that I found was instead of closing the socket by data_socket.close(), I shutdown the socket by data_socket.shutdown(socket.SHUTWR). This tells the server that I will no longer send data, but the server can still continue receiving the data I sent earlier. This allowed the files I uploaded to transfer perfectly to the server.

## How I Tested My Code:
I used the --verbose functionality of my script to check the messages I send to and receive from the server. 
