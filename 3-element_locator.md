## Element locator

To interact with web page we need to find the elements like which button we want to click or which text field we want fill.

Watir provides full power of directly using :css & :xpath selectors.

XPath is syntax or language for finding any element on web page using XML path expresion.

XPath is used to find the location of any element on a webpage using HTML DOM structure.

```xml
Xpath=//tagname[@attribute='value']
```

Example: 

```xml
Xpath=//input[@name='uid']
```
***

**Standard Watir Locators**

### ID

```ruby
browser.div(id: "header")
browser.div(id: /header/)
```

### Name

```ruby
browser.text_field(name: 'new_user_email')
browser.text_field(name: /new_user_email/)
```

### Tag name

```ruby
browser.div
browser.h1
browser.span
```

### Class name

```ruby
browser.text_field(class: 'name')
browser.text_field(class: /name/)
```

### Text

```ruby
# evaluates what is in the DOM, not what a user can see on the page
browser.button(text: "Button 2")
browser.button(text: /Button/)
```

### Visible text

```ruby
# attempts to evaluate based on what a user can see on the page
browser.button(visible_text: "Button 2")
browser.button(visible_text: /Button/)
```

### Data Attributes

```ruby
browser.p(data_type: "ruby-library")
browser.p(data_type: /ruby-library/)
```

### lable

```ruby
# locate based on the value of the associated label element
browser.text_field(label: 'With text'))
browser.text_field(label: /With text/))
```
