# Hackerearth-SDK-PHP
A PHP SDK To Run And Compile Codes Using Hackerearth's API V3

This library helps you to compile and run your code with [HackerEarth API v3](https://www.hackerearth.com/docs/api/developers/code/v3/)

Using HackerEarth API you can compile and run your code using their [CodeTable](https://code.hackerEarth.com)

#### Prerequisite

You have to obtain your client secret key from [HackerEarth Here](http://www.hackerearth.com/api/register/) and voila you are done!

#### Install

>Currently You Can Simply Download A Zip Of This Repo And put this into you code require_once __DIR__.'path\to\folder\sdk\index.php';


>To Use Via [Composer](http://www.getcomposer.com)
```
composer require vipinkhushu/hackerearth-sdk-php
require_once __DIR__.'\sdk\index.php';
```

#### Language Codes
Kindly Use the below codes only to give language name
C, CPP, CPP11, CLOJURE, CSHARP, JAVA, JAVASCRIPT, HASKELL, PERL, PHP, PYTHON, RUBY

#### Set Up

```
//Import the SDK 
require_once __DIR__.'path\sdk\index.php';

//Setting up the Hackerearth API
$hackerearth = Array(
		'client_secret' => 'b1803e335e227a1320fc6dc3587a0d496e97d3e5', //(REQUIRED) Obtain this by registering your app at http://www.hackerearth.com/api/register/
        'time_limit' => '5',   //(OPTIONAL) Time Limit (MAX = 5 seconds )
        'memory_limit' => '262144'  //(OPTIONAL) Memory Limit (MAX = 262144 [256 MB])
	);


```
#### Compile Your code

```
//compile your code 
//Feeding Data Into Hackerearth API
$config = Array();
$config['time']='5';	 	//(OPTIONAL) Your time limit in integer and in unit seconds
$config['memory']='262144'; //(OPTIONAL) Your memory limit in integer and in unit kb
$config['source']='print("Hello! Vipin");';    	//(REQUIRED) Your source code for which you want to use hackerEarth api
$config['input']='';     	//(OPTIONAL) Input against which you have to test your source code
$config['language']='PYTHON';   	//(REQUIRED) Choose any one of them 
						 	// C, CPP, CPP11, CLOJURE, CSHARP, JAVA, JAVASCRIPT, HASKELL, PERL, PHP, PYTHON, RUBY

//Sending request to the API to compile and run and record JSON responses
$responseOfCompile = compile($hackerearth,$config);

```

#### Run Your Code

```
//Run a source code against a input
//Feeding Data Into Hackerearth API
$config = Array();
$config['time']='5';	 	//(OPTIONAL) Your time limit in integer and in unit seconds
$config['memory']='262144'; //(OPTIONAL) Your memory limit in integer and in unit kb
$config['source']='print("Hello! Vipin");';    	//(REQUIRED) Your source code for which you want to use hackerEarth api
$config['input']='';     	//(OPTIONAL) Input against which you have to test your source code
$config['language']='PYTHON';   	//(REQUIRED) Choose any one of them 
						 	// C, CPP, CPP11, CLOJURE, CSHARP, JAVA, JAVASCRIPT, HASKELL, PERL, PHP, PYTHON, RUBY
$responseOfRun = run($hackerearth,$config);

```
#### Compile Your File

```
//compile your code  from a file
//Feeding Data Into Hackerearth API
$config = Array();
$config['time']='5';	 	//(OPTIONAL) Your time limit in integer and in unit seconds
$config['memory']='262144'; //(OPTIONAL) Your memory limit in integer and in unit kb
$config['file']='';			//(REQUIRED WHEN YOU ARE USING A SOURCE FILE) Give the complete address to the file
$config['input']='';     	//(OPTIONAL) Properly Formatted Input against which you have to test your source code
$config['language']='PYTHON';   //(REQUIRED) Choose any one of the below
						 	// C, CPP, CPP11, CLOJURE, CSHARP, JAVA, JAVASCRIPT, HASKELL, PERL, PHP, PYTHON, RUBY


//Sending request to the API to compile and run and record JSON responses
$response = compile_with_file($hackerearth,$config); 

```

#### Run Your File

```
//Run a source code against a input   from a file
//Feeding Data Into Hackerearth API
//Feeding Data Into Hackerearth API
$config = Array();
$config['time']='5';	 	//(OPTIONAL) Your time limit in integer and in unit seconds
$config['memory']='262144'; //(OPTIONAL) Your memory limit in integer and in unit kb
$config['file']='';			//(REQUIRED WHEN YOU ARE USING A SOURCE FILE) Give the complete address to the file
$config['input']='';     	//(OPTIONAL) Properly Formatted Input against which you have to test your source code
$config['language']='PYTHON';   //(REQUIRED) Choose any one of the below
						 	// C, CPP, CPP11, CLOJURE, CSHARP, JAVA, JAVASCRIPT, HASKELL, PERL, PHP, PYTHON, RUBY


//Sending request to the API to compile and run and record JSON responses
$response = run_with_file($hackerearth,$config);

```
#### License
MIT