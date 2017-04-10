# XionMai IPC Video Camera Java Client

This simple project implement connect to XionMaiTech IPC camera, and get the RAW H264 frames.

It will using simple TCP connection to IPC camera, and recv data by a simple TCP client socket.
As the purpose is to migrate to a c program used embeded, so the design is to keep the program same as the c version.

It has been tested with two IPC using Hi3518 3K and 1080P module.

Note: The H264 decoder is not included, you can use javacv + FFMPEG to show in PC.

The protocol is simple, you can refer to the following address for detail.
http://www.ityuedu.com/article/7135512524/

Header 
00-03  ff 00 00 00	
04-07  sessionID	
08-11  requestID
12-13  reserved
14-15  cmd
16-19  payload len

After the login is finished, there are one trick part, need create a new data socket, and execute "claim".
Then the control socket can execute "start". 




