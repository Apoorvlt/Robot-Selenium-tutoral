# Robot Selenium tutorial

![LambdaTest Logo](https://www.lambdatest.com/static/images/logo.svg)


![altext](https://github.com/Apoorvlt/test/blob/master/rfi.PNG)

Robot Framework is a generic open source automation framework. It can be used for test automation and robotic process automation (RPA).
## Prerequisites for Robot Selenium tutorial 

### 1. Python Installation

 * [Download Python](https://www.python.org/downloads/) and click on Add to path and install.
 
 * To check if python installed correctly you need to go to terminal type python in command prompt. It will show you the current version you have downloaded.
 
### 2. LambdaTest Credentials
  * To obtain a username and access_key, sign up for free [here](https://lambdatest.com). After signing up you can find your username and access key [here](https://accounts.lambdatest.com/detail/profile).
  
## Setting Up The Project For Robot Tutorial

  * You can download the file. To do this click on Clone or download button. You can download zip file.
  * Then open the terminal in the folder you want to clone the file. Run the command:
	
	``` 
	git clone https://github.com/LambdaTest/Robot-Selenium-Sample.git
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

![rfst](https://github.com/Apoorvlt/test/blob/master/rfst.PNG)

### Parallel Testing

Parallel Testing is one of the most demanding feature of LambdaTest Selenium Grid. By parallel testing, you can run more than one test case, simultaneously. This means that, Parallel testing would allow you to execute numerous automation test cases altogether. So you execute a single test scenario across different browsers or could run different test scenarios across the same browser but with different browser versions.

To perform parallel testing on LambdaTest Selenium grid use the below command.

```
make run_all_in_parallel
```

![rfpt](https://github.com/Apoorvlt/test/blob/master/rfpt.PNG)


##  Testing Locally Hosted or Privately Hosted Projects

To help you perform cross browser testing of your locally stored web pages, LambdaTest provides an SSH(Secure Shell) tunnel connection with the name Lambda Tunnel. With Lambda Tunnel, you can test your locally hosted files before you make them live over the internet. You could even perform cross browser testing from different IP addresses belonging to various geographic locations. You can also use LambdaTest Tunnel to test web-apps and websites that are permissible inside your corporate firewall.

> OS specific instructions to download and setup tunnel binary can be found at the following links.
>    - [Windows](https://www.lambdatest.com/support/docs/display/TD/Local+Testing+For+Windows)
>    - [Mac](https://www.lambdatest.com/support/docs/display/TD/Local+Testing+For+MacOS)
>    - [Linux](https://www.lambdatest.com/support/docs/display/TD/Local+Testing+For+Linux)

### Important Note:
---
- Some Safari & IE browsers, doesn't support automatic resolution of the URL string "localhost". Therefore if you test on URLs like "http://localhost/" or "http://localhost:8080" etc, you would get an error in these browsers. A possible solution is to use "localhost.lambdatest.com" or replace the string "localhost" with machine IP address. For example if you wanted to test "http://localhost/dashboard" or, and your machine IP is 192.168.2.6 you can instead test on "http://192.168.2.6/dashboard" or "http://localhost.lambdatest.com/dashboard".

## About LambdaTest
[LambdaTest](https://www.lambdatest.com/) is a cloud based selenium grid infrastructure that can help you run automated cross browser compatibility tests on 2000+ different browser and operating system environments. LambdaTest supports all programming languages and frameworks that are supported with Selenium, and have easy integrations with all popular CI/CD platforms. It's a perfect solution to bring your [selenium automation testing](https://www.lambdatest.com/selenium-automation) to cloud based infrastructure that not only helps you increase your test coverage over multiple desktop and mobile browsers, but also allows you to cut down your test execution time by running tests on parallel.

### Resources

##### [Selenium Documentation](http://www.seleniumhq.org/docs/)

##### [Python Documentation](https://docs.python.org/2.7/)
