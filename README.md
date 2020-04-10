# Robot-Selenium-tutorial

![LambdaTest Logo](https://www.lambdatest.com/static/images/logo.svg)

![altext](https://github.com/Apoorvlt/test/blob/master/rfi.PNG)

## Prerequisites for Robot-Selenium-tutorial 


### 1. Python Installation

 * [Download Python](https://www.python.org/downloads/) and click on Add to path and install.
 
 * To check if python installed correctly you need to go to terminal type python in command prompt. It will show you the current version you have downloaded.
 
### 2. LambdaTest Credentials
  * To use Pytest with LambdaTest, make sure you have the 2 environment variables LT_USERNAME and LT_ACCESS_KEY set. To obtain a username and access_key, sign up for free [here](https://lambdatest.com). After signing up you can find your username and access key [here](https://accounts.lambdatest.com/detail/profile).
  * In the terminal export your LambdaTest Credentials as environmental variables:
       
       * For Mac/Linux
            ```
            $ export LT_USERNAME=<your LambdaTest username>
            $ export LT_ACCESS_KEY=<your LambdaTest access key>
            ```
       
       * For Windows
            ```
            set LT_USERNAME=<your LambdaTest username>
            set LT_ACCESS_KEY=<your LambdaTest access key>
    	    ```	
### 3. Setup

  * You can download the file. To do this click on Clone or download button. You can download zip file.
  * Then open the terminal in the folder you want to clone the file. Run the command:
	
	``` 
	git clone https://github.com/Apoorvlt/Pytest-tutorial.git
  	```
  * After Clone or downloading file you need to setup pytest, selenium and virtual environment. It will isolate the build from other setups you may have running and ensure that the tests run with the specified versions of the modules specified in the requirements.txt file. To run the file you need to open terminal in the project folder:
  
	```bash
    pip install -r requirements.txt
    ```
* Create a virtual environment in your project folder the environment name is arbitrary.

	```bash
    virtualenv venv
    ```
  
