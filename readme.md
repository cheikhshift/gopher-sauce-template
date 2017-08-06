# Tutorial on writing templates
Build a website with templates using Go and Gopher Sauce.

![enter image description here](http://www.unixstickers.com/image/data/stickers/golang/Golang%20mashup.sh.png)

### Benefits 

 - Save time
	 - Update once, reused templates.

## Getting started
(unix commands)
					
	mkdir new-project
	cd new-project		
	gos --make

Please make sure your current working directory is `new-project` (or any other name).

## Create /index page
Create new template file :
		
	touch web/index.tmpl

Contents of file (bootstrap 4 starter) : 

		 <!DOCTYPE html>
			<html lang="en">
			  <head>
			    <!-- Required meta tags -->
			    <meta charset="utf-8">
			    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
			
			    <!-- Bootstrap CSS -->
			    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/css/bootstrap.min.css" integrity="sha384-rwoIResjU2yc3z8GV/NPeZWAv56rSmLldC3R/AZzGRnGxQQKnKkoFVhFQhNUwEyJ" crossorigin="anonymous">
			  </head>
			  <body>
			   
			
			    <!-- jQuery first, then Tether, then Bootstrap JS. -->
			    <script src="https://code.jquery.com/jquery-3.1.1.slim.min.js" integrity="sha384-A7FZj7v+d/sdmMqp/nOQwliLvUsJfDHW+k9Omg/a/EheAdgtzNs3hpfag6Ed950n" crossorigin="anonymous"></script>
			    <script src="https://cdnjs.cloudflare.com/ajax/libs/tether/1.4.0/js/tether.min.js" integrity="sha384-DztdAPBWPRXSA/3eYEEUWrWCy7G5KFbe8fFjk5JAIxUYHKkDx6Qin1DkWx51bBrb" crossorigin="anonymous"></script>
			    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-alpha.6/js/bootstrap.min.js" integrity="sha384-vBWWzlZJ8ea9aCX4pEW3rVHjgjt7zpkNpZk+02D9phzyeVkE+jo0ieGizqPLForn" crossorigin="anonymous"></script>
			  </body>
			</html>


## Create templates

### Header
Create new template file :
	
	touch tmpl/header.tmpl

Contents of file : 

		<nav class="navbar navbar-toggleable-md navbar-light bg-faded">
	  <button class="navbar-toggler navbar-toggler-right" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
	    <span class="navbar-toggler-icon"></span>
	  </button>
	  <a class="navbar-brand" href="#">NewWebsite</a>
	
	  <div class="collapse navbar-collapse" id="navbarSupportedContent">
	    <ul class="navbar-nav mr-auto">
	      <li class="nav-item active">
	        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
	      </li>
	      <li class="nav-item">
	        <a class="nav-link" href="#">Link</a>
	      </li>
	      <li class="nav-item">
	        <a class="nav-link disabled" href="#">Disabled</a>
	      </li>
	    </ul>
	   
	  </div>
	</nav>

### Footer
Create new template file :
	
	touch tmpl/footer.tmpl

Contents of file :

	<div style="height:120px" class="page-header"><p>Footer</p></div>

### Add templates to GoS
Edit `gos.gxml`

	nano gos.gxml
		
Add these tags within your `<templates>` tag :
		
	<template name="Header" tmpl="header" struct="" /> 
	<template name="Footer" tmpl="footer" struct="" /> 


### Add templates to web/index.tmpl

Edit `web/index.tmpl`

	nano web/index.tmpl

Add your templates to `web/index.tmpl` :
		
	<body>
     ...
	{{ Header }}
	{{ Footer }}
	...
	</body>


### Testing
Run project :

	gos --run

Visit page : [localhost:8080](http://localhost:8080/)

Download this Repository and run `gos --run` once in directory.