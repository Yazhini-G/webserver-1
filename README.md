# Developing a Simple Webserver

# AIM:

To develop a simple webserver to display about top five programming languages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content ="""
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Welcome to the webserver </h1>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
    
server_address=('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
### client output :
![clientou![serveroutput](https://user-images.githubusercontent.com/120244201/211002658-d09dcc66-de59-40f7-939c-4b85ee38a5ed.png)
tput](https://user-images.githubusercontent.com/120244201/211002640-12e08506-60f1-45de-a859-a0505d6c4fc3.png)
### server-side output:
![serveroutput](https://user-images.githubusercontent.com/120244201/211003362-a9790243-f938-4b39-b1d3-3f17edad089c.png)

## RESULT:
The program is executed succesfully
