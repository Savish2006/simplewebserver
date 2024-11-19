# EX01 Developing a Simple Webserver
## Date: 18-10-2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
<html>
    <title>
        device spec
    </title>
        <h1 align="center">Device Specifications  SAVISH [24900837]
            <ol type="1" start="1">
                <li align="left">   Device Name    :  savish</li>
                <li align="left">   Processor      :  13 th Gen Intel(R) Co
                <li align="left">   Installed RAM  :  16.0 GB (15.7 GB usabl
                <li align="left">   Device ID      :  15Ezy3B2-7EF5-4DEC-903
                <li align="left">   Product ID     :  00342-42708-02761-AAO
                <li align="left">   System Type    :  64-bit operating syste
                <li align="left">   Pen and Touch  :  No pen or touch input 
</ol>    
</h1>
 </h1>
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
![alt text](<Screenshot (38).png>)
![alt text](<Screenshot (39).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
