- # Table of Contents
    - i.  [[Learn the Fundamentals of Node Egghead]]
    - ii. 
- # How to's/Examples/Etc
    - ## How to create a trivial web sever in 6 lines
        - ```javascript
var http = require('http');
http.createServer(function (req, res) { 
  res.writeHead(200, {‘Content-Type’: ‘text/plain’}); 
  res.end(‘Hello World\n’); 
}).listen(1337, ‘127.0.0.1’); 
console.log(‘Server running at http://127.0.0.1:1337/’)


//  The first line requires the http modules, which provide functionality for creating 
//  HTTP clients and servers. Next, a server is started that listens on port 1337. When a 
//  connection is received, the server responds with the message Hello World. The last 
//  line of code simply prints a message to the console in order to let the developer 
//  know what’s happening```
        - 
