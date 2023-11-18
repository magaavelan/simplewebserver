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
<li>Samsung</li>
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
![Screenshot 2023-11-18 095742](https://github.com/magaavelan/simplewebserver/assets/134506532/71f45ab6-1602-469d-8b49-0da6d3ac49dd)


## RESULT:
The program for implementing simple webserver is executed successfully.
