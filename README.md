# Robot-Selenium-tutorial

![LambdaTest Logo](https://www.lambdatest.com/static/images/logo.svg)


![altext](https://github.com/Apoorvlt/test/blob/master/rfi.PNG)


## Prerequisites for Robot-Selenium-tutorial 

### 1. Python Installation

 * [Download Python](https://www.python.org/downloads/) and click on Add to path and install.
 
 * To check if python installed correctly you need to go to terminal type python in command prompt. It will show you the current version you have downloaded.
 
### 2. LambdaTest Credentials
  * To obtain a username and access_key, sign up for free [here](https://lambdatest.com). After signing up you can find your username and access key [here](https://accounts.lambdatest.com/detail/profile).
  
### 3. Setup

  * You can download the file. To do this click on Clone or download button. You can download zip file.
  * Then open the terminal in the folder you want to clone the file. Run the command:
	
	``` 
	git clone https://github.com/Apoorvlt/Pytest-tutorial.git
  	```
  * After Clone or downloading file you need to setup Robotframework and selenium. To do this you need to open terminal in the project folder and run:
  
	```bash
    pip install -r requirements.txt
    ```
## Getting Started With Robot & LambdaTest

Let’ start with a simple Selenium Remote Webdriver test first. The Robot script below tests a simple to-do application with basic functionalities like mark items as done, add items in list, calculate total pending items etc.

Feature: Test to add item Scenario: Test sample-todo-app Given I go to sample-todo-app to add item Then I Click on first checkbox and second checkbox When I enter item to add When I click add button Then I should verify the added item

Here is common.robot file to setup mandatory details to run at LambdaTest.
You would need to your LambdaTest authentication credentials(Access key & Username). You need to update these credentials in the /Resources/Common.robot file.

	```
	${KEY}              YOUR USERNAME:YOUR ACCESS KEY
	EXAMPLE: ${KEY}              username:843908dfslkhfkhfhlkhdsfkl
	```

```
*** Settings ***
Library  Selenium2Library
Library  LambdaTestStatus.py

*** Variables ***

@{_tmp}
    ...  browserName: ${browserName},
    ...  platform: ${platform},
    ...  version: ${version},
    ...  visual: ${visual},
    ...  network: ${network},
    ...  console: ${console},
    ...  name: RobotFramework Lambda Test

${BROWSER}          ${ROBOT_BROWSER}
${CAPABILITIES}     ${EMPTY.join(${_tmp})}
${KEY}              YOUR USERNAME:YOUR ACCESS KEY
${REMOTE_URL}       http://${KEY}@hub.lambdatest.com/wd/hub
${TIMEOUT}          3000

*** Keywords ***

Open test browser
    [Timeout]   ${TIMEOUT}
    Open browser  https://lambdatest.github.io/sample-todo-app/  browser=${BROWSER}
    ...  remote_url=${REMOTE_URL}
    ...  desired_capabilities=${CAPABILITIES}

Close test browser
    Run keyword if  '${REMOTE_URL}' != ''
    ...  Report Lambdatest Status
    ...  ${TEST_NAME} 
    ...  ${TEST_STATUS} 
    Close all browsers
```
### Execute The Test

You would need to execute the below command in your terminal/cmd.


```
make test_Windows_10_chrome_68
```
