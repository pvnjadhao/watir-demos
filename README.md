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

**Test Runner**. In Ruby this can be MiniTest, RSpec or Cucumber. Most Watir users use RSpec by default, but Cucumber is popular for teams that are working in a Behavior Driven Development environment.

**Test Code**. Whether Cucumber Steps or RSpec “it” blocks, the code here should be focused on succinctly representing the business requirement for the test. This is the higher level “what” code that references other objects (like page objects) for the actual implementation. Ruby is more readable than most languages, so name page objects and methods well and a quick skim will allow to the purpose of the test to be easily understood.

**Page Object**. This is where the implementation (“how”) code belongs. Page objects can represent an entire page, a modal, or a subset of a page (like a sidebar or a footer). Page objects are typically comprised of two things, the elements with their applicable locators, and the methods that represent the actions that a user can take on the page. Most of this code will be references to Watir objects.

**Watir Code**. Watir is designed for “Test Automation.” It takes the code in a page object and translates it into the series of applicable Selenium and JavaScript calls to accomplish the desired functionality. Watir attempts to understand the intention of the code in a test suite and tries to follow a “Do What I Mean” philosophy to accomplish it. Continue reading through the documentation to see how Watir makes writing tests fun and easy.

**Selenium Code**. Selenium is designed for “Browser Automation.” It takes the higher focuses on the specific low level actions that can be taken on a browser. It implements a small number of locators and takes a “Do What I Say” approach. It translates idiomatic Ruby code into serialized json blobs to send along for further processing.

**Selenium Server**. This isn’t necessary when driving browsers on the same computer as the code. To drive browsers on a remote computer, though, the commands need to be sent to one or more intermediary servers. The Selenium server can be set to act in a standalone mode, or can be set up as a grid with a server acting as a “hub” on one computer, and a server acting as a “node” on another computer.

**Browser Drivers**. Because of the progress on the W3C WebDriver Specification, each major browser vendor (Google, Microsoft, Apple, and Mozilla) has committed to implementing their own driver for their respective browser. The driver is an executable file that lives on the same machine as the browser that is being automated. Read the Drivers documentation to see how to download and store the driver so that Selenium can find and use it. The driver accepts the standardized information from Selenium code and translates it into code needed by the particular browser to take the action specified.

**Browser**. The browser of your choice executes each command sent by the driver, and sends the results or errors back down this path to the test code.

