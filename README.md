# EX01 Developing a Simple Webserver

# Date:
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
content="""
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Laptop Configuration</title>
    <style>
        
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
        }

        
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-top: 30px;
            font-size: 36px;
        }

        
        table {
            width: 70%;
            margin: 30px auto;
            border-collapse: collapse;
            border-radius: 8px;
            overflow: hidden;
            background-color: #fff;
            border: 5px solid #333; 
        }

        
        th {
            background-color: #1ae67c;
            color: white;
            padding: 15px;
            font-size: 20px;
            text-align: left;
            border: 2px solid #333; 
        }

        
        td {
            background-color: #1ae67c;
            padding: 12px;
            text-align: left;
            font-size: 18px;
            border: 1px solid #333; 
        }

        
        tr:nth-child(even) {
            background-color: #ecf0f1;
        }

    
        tr:hover {
            background-color: #1ae67c;
            color: white;
        }

        
        table {
            box-shadow: 0px 0px 15px rgba(0, 0, 0, 0.1);
        }

    
        td, th {
            padding: 15px;
        }

        
        @media (max-width: 768px) {
            table {
                width: 90%;
            }
            th, td {
                font-size: 16px;
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <h1>LAPTOP CONFIGURATION</h1>
    <table>
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Model</td>
            <td>Lenovo</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i5</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16GB</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>256GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>Integrated Intel UHD Graphics</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>14-inch FHD (1920 x 1080)</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 10</td>
        </tr>
        <tr>
            <td>Colours available</td>
            <td>Black, White, Grey</td>
        </tr>
    </table>
</body>
</html>
"""
class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer (server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2024-12-07 032754.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
