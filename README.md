# EX01 Developing a Simple Webserver
## Date:
21/11/2024
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
<head>
<title>
    simple webserver
</title>
    <h1 align="center">Device Specifications (Syed Kashif S [24006084])
        <ol type="1" start="1">
            <li align="left"> Device Name : kashif-LAP</li>
            <li align="left"> Processor : 13th Gen Intel(R) Core(TM
            <li align="left"> Installed RAM : 16.0 GB (15.7 GB usable)</
            <li align="left"> Device ID : 15EEA3B2-7EF5-4DEC-903D-57
            <li align="left"> Product ID : 00342-42709-07143-AAOEM</l
            <li align="left"> System Type : 64-bit operating system, x
            <li align="left"> Pen and Touch : No pen or touch input is a
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

![alt text](<Screenshot (26).png>)
![alt text](<Screenshot (27).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
