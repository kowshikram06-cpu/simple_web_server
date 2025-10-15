# EX01 Developing a Simple Webserver

# Date:14.10.2025
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
from http.server import HTTPServer, BaseHTTPRequestHandler 
content = """ 
<!DOCTYPE html> 
<html> 
<head> 
<title>Simple Web Server</title> 
</head> 
<body> 
<h1 align="center">19AI414-Fundamentals of Web Application Development</h1> 
<h2>Execrise 1: Simple Web Server</h2> 
<pre>Status: Completed Successfully!!!!</pre> 
</body> 
</html> 
""" 
class SimpleWebServer(BaseHTTPRequestHandler): 
    def do_GET(self): 
        print("request received") 
        self.send_response(200) 
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers() 
        self.wfile.write(content.encode()) 
server_address = ('',8080) 
httpd = HTTPServer(server_address,SimpleWebServer) 
print("my webserver is running...") 
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2025-10-15 112504.png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
