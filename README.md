# EX01 Developing a Simple Webserver
## Date: 25.10.24

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''

<html>
<head>
    <title>My Web Server</title>
</head>
<body>
    <h1>Laptop Configuration</h1>
    <table border="1" cellpadding="10">
        <tr>
            <th>Attribute</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>VINAY SUHIRTHAN</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>12th Gen Intel(R) Core(TM) i5-12450HX 4.80 GHz</td>
        </tr>
        <tr>
            <td>GPU</td>
            <td>Nvidia GeFORCE RTX 3050 (6GB RAM)</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>32.0 GB (31.4 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>41D7B1D43-5B95-4C99-9B29-924CA65A75A9</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00659-42682-24684-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input available for this display</td>
        </tr>
    </table>
</body>
</html>
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


## OUTPUT:

![Screenshot 2024-10-25 222652](https://github.com/user-attachments/assets/e29fddad-0a0e-441f-8fe9-b487423e0d5c)
![Screenshot 2024-10-25 222713](https://github.com/user-attachments/assets/01d203ca-82b1-4284-9d1d-d2df3009f7ec)


## RESULT:
The program for implementing simple webserver is executed successfully.
