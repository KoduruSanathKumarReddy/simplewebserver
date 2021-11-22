# Developing a Simple Webserver
## AIM:
To develop a simple webserver to show top 5 Programming Languages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>SimpleWebserver</title>
</head>
<body>
<h1>Five Programing languages</h1>


<h2>1. Swift Programming Language</h2>

<h3>Swift is a fantastic way to write software, whether it’s for phones, desktops, servers, or anything else that runs code. It’s a safe, fast, and interactive programming language that combines the best in modern language thinking with wisdom from the wider Apple engineering culture and the diverse contributions from its open-source community. The compiler is optimized for performance and the language is optimized for development, without compromising on either.</h3>
<br>
<h2>2. Java Programming Language</h2>

<h3>Java is a platform as well as a programming language. Java is a high-level programming language that is also robust, object-oriented, and secure. </h3>

<h3>Java was created in 1995 by Sun Microsystems (which is now a division of Oracle). The founder of Java, James Gosling, is recognised as the "Father of Java." It was known as Oak before Java. Because Oak was already a recognised business, James Gosling and his team decided to alter the name to Java.</h3>
<br>
<h2>3. Python Programming Language</h2>

<h3> Python is a programming language that is commonly used to create websites and applications, automate operations, and perform data analysis. Python is a general-purpose programming language, which means it can be used to develop a wide range of applications and isn't specialised for any particular problem. Because of its versatility and beginner-friendliness, it has become one of the most widely used programming languages today. It was the most popular programming language among developers in 2020, according to a survey done by industry analytics firm RedMonk . </h3>
<br>
<h2>4. C Programming Language</h2>

<h3>Dennis Ritchie created the C programming language for constructing system applications that interact directly with hardware components such as drivers, kernels, and so on. C programming is known as the mother language because it serves as a foundation for other programming languages.</h3>
<br>
<h2>5. R Programming Language</h2>

<h3> R is a statistical computing and graphics language and environment. It is a GNU project that is similar to the S language and environment established by John Chambers and colleagues at Bell Laboratories (previously AT&T, now Lucent Technologies). R can be thought of as a more advanced version of S. Although there are some significant differences, much of the code built for S works in R without modification.
<br>
R is a statistical computing and graphics language and environment. It is a GNU project that is similar to the S language and environment established by John Chambers and colleagues at Bell Laboratories (previously AT&T, now Lucent Technologies). R can be thought of as a more advanced version of S. Although there are some significant differences, much of the code built for S works in R without modification.
</h3>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:


## RESULT: This is a program to display about 5 programming languages.
