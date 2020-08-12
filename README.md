# open-http-puncher
This is for advanced users only.
This was intended to release the last month, I am sorry for the delay.

This is a tool that helps you to bypass internet firewall using HTTP.
This will force your server to send HTTP connection established response.

HTTP tunneling client -> Firewall -> ohpserver
Features:
Upgrades your HTTP Proxy software (squid/tinyproxy/privoxy) to an HTTP tunneling friendly
Allows invalid HTTP request to be sent to the server and responses 200 automatically

The client is optional but you can use it on your routers/mobile or computer depends on the architecture

Install Guide (Linux):

Install any HTTP Proxy Software first and make sure it works
`wget https://github.com/lfasmpao/open-http-puncher/releases/download/0.1/ohpserver-linux32.zip
unzip ohpserver-linux32.zip
chmod +x ohpserver`

Run server (Linux)
`screen -dm bash -c "./ohpserver.exe -port (server port) -proxy (HTTP proxy ip:port) -tunnel (redirection tunnel ip:port)"`
Run server (Windows):
Open CMD and cd to the directory
`ohpserver.exe -port (server port) -proxy (HTTP proxy ip:port) -tunnel (redirection tunnel ip:port)`

Sample Server Usage:
Windows:
SSH
`ohpserver.exe -port 5555  -proxy 127.0.0.1:3128 -tunnel 127.0.0.1:22`

OpenVPN
`ohpserver.exe -port 5555  -proxy 127.0.0.1:3128 -tunnel 127.0.0.1:1194`

Linux:
SSH
`./ohpserver -port 5555  -proxy 127.0.0.1:3128 -tunnel 127.0.0.1:22`

OpenVPN
`./ohpserver -port 5555  -proxy 127.0.0.1:3128 -tunnel 127.0.0.1:1194`

You could use external IP and port

Using the server on your HTTP Tunneling client:
Setup your HTTP Tunneling client to use the server as your HTTP Proxy and input any IP on your SSH/VPN client it will be automatically redirected to the one you've set into your server (tunnel)
Note: This is only a server you could use any HTTP tunneling client that sends HTTP requests to a server
