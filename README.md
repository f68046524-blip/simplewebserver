# EX01 Developing a Simple Webserver
## Date:28/09/26

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title> my hobbies </title>
    </head>
    <body bgcolor="white">
<h1 align="center">FAISAL</h1>
<h2 align="center">26018146</h2>
<u>Table</u>
<table border="1" cellspacing="5" cellpading="5">
    <caption><b><u><h1>aboutlaptop</h1></u></b></caption>
    <tr>
        <th>SNO</th>
        <th>DEVICE TYPE</th>
        <th>info</th>
    </tr>
    <tr>
        <th>1</th>
        <td>Devicename</td>
        <td>FAISAL@2008</td>
    </tr>
    <tr>
        <th>2</th>
        <td>processor</td>
        <td>intel i5</td>
    </tr>
    <tr>
        <th>3</th>
        <td>ram</td>
        <td>16gb</td>
    </tr>
    <tr>
        <th>4</th>
        <td>graphics</td>
        <td>intel128</td>
    </tr>
        <tr>
            <th>5</th>
            <td>storage</td>
            <td>512</td>
        </tr>
  </table>
 </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()
```


## OUTPUT:
web page
![alt text](<Screenshot 2026-10-21 085640.png>)
web server
![alt text](<Screenshot 2026-10-21 090056.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
