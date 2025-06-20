# EX01 Developing a Simple Webserver

# Date: 03/03/2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''
<h2>TCP/IP Protocol Suite</h2>

<table border="1">
    <tr>
        <th>Layer</th>
        <th>Protocols</th>
    </tr>
    <tr>
        <td>Application Layer</td>
        <td>HTTP, HTTPS, FTP, SMTP, DNS, DHCP, Telnet, SNMP</td>
    </tr>
    <tr>
        <td>Transport Layer</td>
        <td>TCP, UDP</td>
    </tr>
    <tr>
        <td>Internet Layer</td>
        <td>IP, ICMP, ARP, IGMP</td>
    </tr>
    <tr>
        <td>Network Access Layer</td>
        <td>Ethernet, Wi-Fi, PPP</td>
    </tr>
</table>
'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

```

# OUTPUT:
![alt text](<Screenshot (11).png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
