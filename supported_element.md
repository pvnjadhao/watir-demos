## Supported Elements

Here are some basic examples for interacting with elements:

### Text Fields

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
name = browser.text_field id: 'user_name'
name.exists?
name.set 'Dany'
name.value
```

### Select Lists – Combos

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
select_lang = browser.select_list id: 'languages'
select_lang.select 'Ruby'
select_lang.selected_options
```

### Radios

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
gem = browser.radio value: 'A gem'
gem.exists?
gem.set
gem.set?
```

### Checkboxes

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
ruby_version = browser.checkbox value: '1.9.2'
ruby_version.exists?
ruby_version.set
ruby_version.set?
```

### Buttons

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
login_btn = browser.button value: 'Submit'
login_btn.exists?
login_btn.click
```

### Links

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
form_link = browser.link text: 'Google Forms'
form_link.exists?
form_link.click
```

### Divs & Spans

```ruby
browser = Watir::Browser.start 'http://localhost:3000'
d = browser.div class: 'col-md-12 custom-column'
d.exists?
d.text
s = browser.span class: 'powered-by-text'
s.exists?
s.text
```
