# EX01 Developing a Simple Webserver
## Date:20/3/2024

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

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
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>TCP/IP Protocol </title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f2f6fc;
      color: #333;
      padding: 20px;
    }

    header {
      background: linear-gradient(90deg, #0d47a1, #1976d2);
      padding: 20px;
      text-align: center;
      color: white;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.2);
      margin-bottom: 30px;
    }

    header h1 {
      font-size: 2.5em;
      letter-spacing: 1px;
    }

    .layer {
      background-color: white;
      padding: 20px;
      margin-bottom: 20px;
      border-left: 6px solid #1976d2;
      border-radius: 10px;
      transition: transform 0.2s, box-shadow 0.2s;
      box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    }

    .layer:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 16px rgba(0,0,0,0.15);
    }

    .layer h2 {
      color: #0d47a1;
      margin-bottom: 10px;
    }

    ul {
      list-style-type: disc;
      padding-left: 25px;
    }

    ul li {
      padding: 5px 0;
    }

    footer {
      text-align: center;
      margin-top: 40px;
      color: #777;
    }
  </style>
</head>
<body>

  <header>
    <h1>TCP/IP Protocol 🛜</h1>
  </header>

  <div class="layer">
    <h2>1. Application Layer</h2>
    <ul>
      <li>HTTP</li>
      <li>FTP</li>
      <li>SMTP</li>
      <li>DNS</li>
      <li>Telnet</li>
      <li>SSH</li>
    </ul>
  </div>

  <div class="layer">
    <h2>2. Transport Layer</h2>
    <ul>
      <li>TCP (Transmission Control Protocol)</li>
      <li>UDP (User Datagram Protocol)</li>
    </ul>
  </div>

  <div class="layer">
    <h2>3. Internet Layer</h2>
    <ul>
      <li>IP (Internet Protocol)</li>
      <li>ICMP (Internet Control Message Protocol)</li>
      <li>ARP (Address Resolution Protocol)</li>
      <li>IGMP (Internet Group Management Protocol)</li>
    </ul>
  </div>

  <div class="layer">
    <h2>4. Network Access Layer</h2>
    <ul>
      <li>Ethernet</li>
      <li>Wi-Fi</li>
      <li>PPP (Point-to-Point Protocol)</li>
    </ul>
  </div>

  <footer>
    <p>&copy; 2025 Paul Shervin | TCP/IP</p>
  </footer>

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
![alt text](image-2.png)
![output2](image-1.png)


## RESULT:
The program for implementing simple webserver is executed successfully.
