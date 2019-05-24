## Advance Usage of Watir

### Measure Page Performance

Watir provides gem to measure the performance of the page.

This is a perfect solution to capture response time metrics, and it’s very straightforward to do. 

Works in Chrome, Firefox, Edge and IE9. Currently no Safari support.

```ruby
require 'watir'
require 'watir-performance'

10.times do
  b = Watir::Browser.new :chrome
  b.goto 'http://www.google.com'
  load_secs = b.performance.summary[:response_time] / 1000
  puts "Load Time: #{load_secs} seconds."
  b.close
end
```

List of available metrics :

* ```:summary```
* ```:navigation```
* ```:memory```
* ```:timing```

Available metric options :

```ruby
{
  :summary => {
                 :redirect=>0,
                :app_cache=>0,
                      :dns=>0,
          :tcp_connection=>982,
   :tcp_connection_secure=>721,
                :request=>1222,
                  :response=>4,
         :dom_processing=>4293,
          :response_time=>7298,
     :time_to_first_byte=>2205,
      :time_to_last_byte=>2209
  },
  :navigation => {
                   :type => 0,
      :type_back_forward => 2,
         :redirect_count => 0,
          :type_reserved => 255,
          :type_navigate => 0,
            :type_reload => 1
  },
  :memory => {
      :total_js_heap_size => 0,
      :js_heap_size_limit => 0,
       :used_js_heap_size => 0
  },
  :timing => {
               :domain_lookup_start => 1303180421599,
                    :load_event_end => 0,
                       :connect_end => 1303180421642,
                      :response_end => 1303180421853,
                       :dom_loading => 1303180421840,
                  :navigation_start => 0,
                      :redirect_end => 0,
                :unload_event_start => 0,
           :secure_connection_start => 0,
                     :connect_start => 1303180421600,
      :dom_content_loaded_event_end => 1303180421934,
                 :domain_lookup_end => 1303180421600,
                   :dom_interactive => 1303180421934,
                  :load_event_start => 0,
                     :request_start => 1303180421642,
                    :response_start => 1303180421838,
                      :dom_complete => 0,
                       :fetch_start => 1303180421598,
    :dom_content_loaded_event_start => 1303180421934,
                    :redirect_start => 0,
                  :unload_event_end => 0
  }
}
```
***

### Headless mode
A headless browser is a web browser without a graphical user interface. Headless browsers provide automated control of a web page in an environment similar to popular web browsers, but are executed via a command-line interface or using network communication.

```ruby
require 'watir'

browser = Watir::Browser.new(
  :chrome,
  {
    :chromeOptions => {
      :args => ['--headless', '--window-size=1200x600']
      }
    }
  )
browser.goto('https://www.cryptextechnologies.com/')
browser.screenshot.save 'screenshot.png'
```
***

### Special Keys

To send special keys to an element or browser page, you use the #send_keys method.

```ruby
b.send_keys :enter
```

Use keys on elements

```ruby
b.element.send_keys [:control, 'a'], :backspace
```

List of keys available:

```ruby
:cancel
:help
:backspace
:tab
:clear
:return
:enter
:shift
:left_shift
:control
:left_control
:alt
:left_alt
:pause
:escape
:space
:page_up
:page_down
:end
:home
:left
:arrow_left
:up
:arrow_up
:right
:arrow_right
:down
:arrow_down
:insert
:delete
:semicolon
:equals
:numpad0
:numpad1
:numpad2
:numpad3
:numpad4
:numpad5
:numpad6
:numpad7
:numpad8
:numpad9
:multiply
:add
:separator
:subtract
:decimal
:divide
:f1
:f2
:f3
:f4
:f5
:f6
:f7
:f8
:f9
:f10
:f11
:f12
```
