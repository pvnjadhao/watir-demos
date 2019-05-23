# Presentation

Good morning everyone,

I am Pavan Jadhao, Ruby on Rails developer.

Today I am going to discuss about Watir gem. This is Overview of my presentation.

* What is Watir?
* How to create environment to use watir?
* How it works?
* How to use it?
* Comparison of Watir with other tools
* References

```bash
Q. Anybody knows what is Watir and its applications?
```

### What is Watir?

- A Watir stands for **Web Application Testing In Ruby**. It is also as Watir-Webdriver.

- Its an open source Ruby library for writing automated tests.

- Watir interacts with a browser the same way people do by clicking links, filling out forms, validating text, resizing browser window and it also measure the performance of pages.

- The latest version of Watir is 6.16. The watir tests developed and run against the brower.
***

### How to create environment to use watir?

- Before going further lets see how to setup a testing environment using Watir.
- To setup environment we need to install couple of things like

* Ruby
* Watir gem
* Drivers

- Everyone knows how to install Ruby and Ruby gem. Here is the list of browser driver. 

- So, What is webdriver

```bash
Q. Anybody knows what is webdriver and why we need this?
```
- WebDriver communicates with the browser using an specific protocol called the WebDriver JSON Wire Protocol.

There are multiple browser vendors like

* Google
* Mozilla
* Microsoft
* Apple

and others.

- So we need to install drivers for different browsers.
- Google chrome supports chromedriver
- Mozilla supports Geckodriver
- Microsoft edge supports microsoft web-driver
- Safari supports safari driver if you are on MAC there is no need to install driver for safari it is preinstalled.

- So, How to install the driver for browsers in ubuntu. Its so simple just go to official site of browser and download the driver, but you need to carefull about browser verion.

- There is directory in ubuntu **/usr/bin/** just copy the downloaded file in bin directory.
***

### How Watir works?
Watir is a user focused way to test your websites. It mostly uses Selenium for browser automation, but it provides many more high level features that make it easy to write stable, maintainable tests.

The typical flow of information looks like this:

Test Runner –>   
      Test code –>   
           PageObject code –>   
                Watir library–>   
                     Selenium library –>   
                          Selenium Server(s) (optional) –>   
                               Browser Driver –>   
                                    Browser  

**Test Runner**. In Ruby this can be MiniTest, RSpec or Cucumber. It is responsible for running test suite. Most developers uses RSpec by default.

**Test Code**. If you are using Rspec then its an “it” blocks, the code here focused on representing the business requirement for the test.

**Page Object**. Page objects represent an entire page which is rendered on browser, a modal, or a subset of a page like a sidebar or a footer. The page object is nothing but the collection of html elements with selectors like classes, ids and data-attributes.

**Watir Code**. Watir takes the code in a page object and translates it into the series of Selenium and JavaScript calls to simulate the user behaviour.

**Selenium Code**. Selenium is designed for “Browser Automation.” It takes the higher focuses on the specific low level actions that can be taken on a browser. It translates Ruby code into serialized json blobs to processing.

**Selenium Server**. This is not necessary when driving browsers on the same computer as the code. Selenium servers are useful when you want drive a browser on remote computer.

**Browser Drivers**. The driver is an executable file that present on the same machine where the browser. It takes command from selenium code and sends to browser and browser will perform the actions. 

**Browser**. The browser of your choice executes each command sent by the driver, and sends the results or errors back to the test code.

