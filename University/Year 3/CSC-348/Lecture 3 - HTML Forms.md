#### HTML Forms
- A fundamental method for collecting information from the user within a browser and adding it to the request
- Data can be sent via 2 methods:
	- GET
		- encodes the data within the URL
		- (a "pls give me" request, followed by data being sent from the server to the user)
	- POST
		- Adds named variables to the HTTP request headers
		- Posting data (like comments on posts)
- You dont need a server to test HTML forms, you can just create a HTML file and view it in the browser.
	``` 
	<form>
		<input name = "q"/>
	</form>
	```
- ^ Forms start with the \<form> tag and contain form elements.
``` 
< form method="get" action = "http://www.google.com/search">
	<input name="q"/>
	<input type="submit"/>
</form>
```
^ The action attribute specified where to send the form data to. By default a form uses a get method (so the method = "get" isnt needed, but its good practice to)
- **The interface of development tools changes a lot. At the moment its under "payload"**

#### "GET" FORM METHOD (Default one)
- Parameters and data is included in the URL
- Often used for fetching documents (getting)
- Limited by maximum URL Length (depends on browser)
- Okay to cache
- Should not change server
- Simple fetching parameters (like video id on youtube)

#### "POST" FORM METHOD
- Parameters and data are in the body of the HTTP request after the headers
- Often used for updating data (Posting)
- No maximum length
- Not okay to cache
- Okay to change the server
- Used for making server updates

#### Serverside Logic: 
- The first step towards dynamic responses was CGI (common gateway interface)
- It let web servers interface with executable programs (installed on the server)
	- Done by the server supplying form data to the executable (through standard input for POST method) and (environment variables for GET method)
	- Executable then processes data and outputs a string which is a HTML file which the server sends back to browser

#### Issues with CGI: 
- It was kinda hacked together so had issues.
- Code in CGI scripts mixes responsibility so theres no separation between code managing logic and code managing appearance
- Scripts always had to output the entire HTML page so lots of code repeated
- CGI scripts were executables running on the server machine outside the web server software so theres like.... security issues with that

#### A FIX: PHP!
- Personal Home Page
-  Started as a set of CGI scripts, more functionality was added after the fact and is now public and open source 
- It's an interpreted language! (like python)
	- PHP parsing engine on the server parses the PHP files and performs the tasks
- **PHP runs within the web server software, so we cant test PHP code without a web server running**
- PHP is entered in between <?php ?> tags 
- "echo" outputs variables, as it does in the linux CLI (if ur reading my notes and dont know about linux commands sort it out lad)
- If we put HTML tags in the output, theyll be interpreted by our browser
``` <!DOCTYPE html>
	<html>
	<body>
	<?php
	echo "My first PHP script!";
	?>
	
	</body>
	</html>
```
^ you can echo html btw! like \<h1> BLAH BLAH BLAH \<\h1>;
- Variables need not be declared
- They must, however, start with $
- This is to simplify parsing ^^
- There is no php source in the html the browser recieves


#### A Simple Calculator in HTML and PHP!
```
<!DOCTYPE html>
<html>
<body>

<header>
	<h1>Simple HTML Calculator</h1>
</header>

<section>
	<form method="get" actions="script4.php">
		<input name="v1"/>
		<select name="action">
			<option value = "plus">+</option>
			<option value = "minus">-</option>
		</select>
		<input name = "v2"/>
		<input type="submit" name="submit" value="Submit"/>
	</form>
</section>

</body>
</html>
```
^ This is the HTML part. Note the "script4.php" being called! Below is the PHP!
```
<?php
	//Check to see if the submit button has been hit
	if (isset($_GET["submit"])){
		//Get and store the variables
		$v1 = $_GET["v1"];
		$v2 = $_GET["v2"];
		
		//Check which operation is required and perform it
		if($_GET["action"] == "plus"){
			$result = $v1 + $v2;
			echo "= $result";
		} else {
			$result = $v1 - $v2;
			echo "= $result";
		}
	}
?>
```
^ Note we need to check to see if the button has been hit because web apps dont have a concept of state! Crazy shit.
- Youll have to refresh the whole page for the answer right now, AJAX is something we will come to later which does address this limitation.

#### Issues with "raw" PHP
- It doesnt solve the issues of repeated code and mixed responsibilities.
- The fix? Laravel! (A web framework