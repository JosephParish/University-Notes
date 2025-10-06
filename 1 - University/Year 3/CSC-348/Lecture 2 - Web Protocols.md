#### URLs:
- Uniform Resource Locator
- Protocol :// Host Path
	- Protocol: "http"
	- Host: www.farmingsimulator.com
		- The host is the unique address of the server we're accessing. It's converted into an IP address by a DNS server.
	- Path: /index.html

#### Query Parameters (or GET params)
- youtube.com/watch?v=dQw4
	- the ?v=dQw4 is a query parameter in which the data is encoded as an addon to the URL
		- ?name = value format
	- You can have multiple get parameters, split them with an &
		- ?v=dQw4&t=30s
			- ^ video id, 30 seconds in
- GET parameters are readable in the URL bar and are sent to the server as part of the request

#### Fragments
- Not sent to the server
- Can do a wide range of things, actioned in the browser
- NOT sent to the server

#### Server - Browser Request - Response flow
1. Handshake
2. Browser sends HTTP request to the server
3. Server sends a HTTP response back

#### HTTP Requests: 
- HTTP:
	- Hyper
	- Text
	- Transfer 
	- Protocol
- Can be thought of as a text file the browser sends to the server
- The request from a browser for a URL begins with the request line
- E.G:  https://www.w3.org/Protocols in the URL bar
	- Request line: GET/Protocols HTTP/1.1
		- Method (type of request making) -> GET
		- Path (path we are requesting from host) -> /Protocols
		- Version of HTTP we use
	- **^ note the host is not in the request because we connect to it before we make this request**

-- After this, we get a list of headers in Name: value pairs --

#### HTTP Request Headers: 
- The full request is made up of the request line (above) followed by the Name:Value pairs.
- E.G: 
	- GET /Protocols HTTP1.1
	- Host: www.w3.org
	- User-agent: chrome v.17

- Host is useful because web servers hold many websites. We're connected to the correct machine already before making this request however, keep that in mind.
- User agents are important for security as some traffic isnt from browsers, like google crawler! 

#### HTTP Response: 
- The response from the server begins with a status line:
- HTTP/1.1 200 OK
	- HTTP/1.1 -> Version
	- 200 -> Status code
	- OK -> English language description of status code

#### STATUS CODES:
- 1xx -> Information that things are still going on
- 2xx -> Success of some kind
- 3xx -> Redirection
- 4xx -> Client error
- 5xx -> Server error

#### HTTP Response Headers:
- Just like with requests, theyre name value pairs.
- They give minimal info to help prevent attacks.
- Usually followed by the content.
	- HTTP/1.1 200 OK
	- Date: Mon June 2016 15:49:22 GMT
	- Server: Apache /2.2.3
	- Content-Type: text/html
	- Content-Length: 1346

#### How do we move towards interactive Web Apps? 
- To enable web app responses dynamically we need the followng:
	- A way for the user to send data to the server (via browser)
		- HTML Forms
	- A way for the server to change what it sends to the user based on the data it recieves
		- Server side logic