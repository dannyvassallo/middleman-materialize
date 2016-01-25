![Middleman Logo](https://s3.amazonaws.com/middlemantemplate/materialize.png "Middleman Logo")
#Middleman 4 / Materialize CSS Boilerplate

*Oh It's so f@!king nice.*

####What does it do?
This boilerplate is set up to increase my workflow. Hopefully, this can also help you on your way.
Follow the deployment instructions below to deploy to heroku.
There is also a partial/template for meta info on most social networks.

####Technologies Used
* Ruby
* Middleman v4
* ERB
* HTML5
* CSS3
* SASS
* jQuery
* Font Awesome
* Minify HTML gem
* GA gem
* [MaterializeCSS](http://materializecss.com/) Sass

####Getting Started
Clone the repo using the GUI or terminal. To do so in terminal, use the following:
```shell
git clone https://github.com/dannyvassallo/middleman-materialize.git
cd middleman-materialize
```

From the "middleman-materialize" directory, install the gems by running the following:
```shell
bundle install
```

To fire up the server while in the "middleman-materialize" directory use this command:
```shell
middleman s
```

If you are having issues with livereload not working fire up the server using:
```shell
middleman s --force-polling --verbose
```

To kill the server use "ctrl+c"

If you find yourself curious as to what directory you are in use the following in terminal:
```shell
pwd
```
It should turn up "middleman-materialize"

####Analytics Setup

Add this setup with your id to the `config.rb` file.

```ruby
#config.rb

activate :google_analytics do |ga|
  # Property ID (default = nil)
  ga.tracking_id = 'UA-XXXXXXX-X'

  # Removing the last octet of the IP address (default = false)
  ga.anonymize_ip = false

  # Tracking across a domain and its subdomains (default = nil)
  ga.domain_name = 'example.com'

  # Tracking across multiple domains and subdomains (default = false)
  ga.allow_linker = false

  # Tracking Code Debugger (default = false)
  ga.debug = false

  # Tracking in development environment (default = true)
  ga.development = true

  # Compress the JavaScript code (default = false)
  ga.minify = false

  # Output style - :html includes <script> tag (default = :html)
  ga.output = :js
end
```

####Deploy
This step requires a heroku account

Create an app (Run Once)
```shell
heroku create <<MYAPP>>
```

Initial Setup (Run Once)
```shell
heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

Deploying (Every deploy)
```shell
git push heroku master
```

####Middleman Helper Methods

Create an external link:
```html
<%= link_to 'My Site', 'http://mysite.com' %>
```

Create an internal link:
```html
<%= link_to 'About', '/about.html' %>
```

Link / Image tag for image in images folder:
```html
<% link_to 'http://mysite.com' do %>
  <%= image_tag 'mylogo.png' %>
<% end %>
```

Create a form (example):
```html
<% form_tag '/destroy', :class => 'destroy-form', :method => 'delete' do %>
  <% field_set_tag do %>
    <p>
      <%= label_tag :username, :class => 'first' %>
      <%= text_field_tag :username, :value => params[:username] %>
    </p>
    <p>
      <%= label_tag :password, :class => 'first' %>
      <%= password_field_tag :password, :value => params[:password] %>
    </p>
    <p>
      <%= label_tag :strategy %>
      <%= select_tag :strategy, :options => ['delete', 'destroy'],
          :selected => 'delete' %>
    </p>
    <p>
      <%= check_box_tag :confirm_delete %>
    </p>
  <% end %>
  <% field_set_tag(:class => 'buttons') do %>
    <%= submit_tag "Remove" %>
  <% end %>
<% end %>
```

Text helpers for dummy info:

USAGE:
```html
<%= lorem.sentences 5 %>
```

DIFFERENT METHODS:
```ruby
lorem.sentence      # returns a single sentence
lorem.words 5       # returns 5 individual words
lorem.word
lorem.paragraphs 10 # returns 10 paragraphs
lorem.paragraph
lorem.date          # accepts a strftime format argument
lorem.name
lorem.first_name
lorem.last_name
lorem.email
```

Placeholder Images:

USAGE:
```html
<%= lorem.image('300x400') %>
```

DIFFERENT METHODS:
```ruby
lorem.image('300x400')
  #=> http://placehold.it/300x400
lorem.image('300x400', :background_color => '333', :color => 'fff')
  #=> http://placehold.it/300x400/333/fff
lorem.image('300x400', :random_color => true)
  #=> http://placehold.it/300x400/f47av7/9fbc34d
lorem.image('300x400', :text => 'blah')
  #=> http://placehold.it/300x400&text=blah
```
