# EX 01 Developing a Simple Webserver
## Date: 19/09/2023
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Top 5 Revenue Generating Companies</u><h1>
<ul>
<li>Apple</li>
<li>Amazon</li>
<li>Microsoft</li>
<li>Samsung</li>
<li>Google</li>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2023-10-21 090057](https://github.com/Darkwebnew/simplewebserver/assets/143114486/853ad8a8-121f-4f4e-928d-8e5a28e1c588)
![Screenshot 2023-10-21 090026](https://github.com/Darkwebnew/simplewebserver/assets/143114486/1ff76aee-137f-490f-a5e6-5b6caee76b71)

## RESULT:
The program for implementing simple webserver is executed successfully.
