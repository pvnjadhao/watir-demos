### Simple Ruby script

```ruby
require 'watir'

browser = Watir::Browser.new
browser.goto 'https://www.cryptextechnologies.com/'

puts browser.title
# => Ruby on Rails Development Company in India | Cryptex Technologies

browser.close
```

Run the test

```bash
$ ruby sample_test.rb
```

***

### Integration with Mini-Test
This is a simples usage of Watir and Minitest. You do not have to install anything, MiniTest is included in Ruby.

```ruby
require 'minitest/autorun'
require 'watir'

class CryptexContactPage < MiniTest::Unit::TestCase
  def test_there_should_be_text_About_Us
    browser = Watir::Browser.new
    browser.goto("https://www.cryptextechnologies.com/")
    assert(browser.text.include?("About Us"))
  end
end
```

Run mini test

```bash
$ ruby sample_test.rb
```

***

### Integration with rSpec
To use Watir with rSpec we first need to install **rspec** gem.

```bash
$ gem install rspec
```

Load the rspec gem into the ruby script and its done!

```ruby
require 'rspec'
require 'watir'

browser = Watir::Browser.new

RSpec.configure do |config|
  config.before(:each) { @browser = browser }
  config.after(:suite) { browser.close unless browser.nil? }
  config.expect_with :rspec do |expectations|
    expectations.syntax = :should
  end
end

describe "demonstration of watir and RSpec" do
  before(:each) do
    @browser.goto("https://www.google.com/")
  end

  describe "that we have hit a valid URL" do
    it "should not return an invalid error message" do
      @browser.text.should_not include('The requested URL could not be retrieved')
    end
  end
end
```

Run the test

```bash
$ rspec sample_test.rb
```

