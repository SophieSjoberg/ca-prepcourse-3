## Sinatra - first steps

In your terminal create a project folder:
```
mkdir my_app
```
cd into that folder and run the following command to install `rspec-sinatra` 

```shell
$ gem install rspec-sinatra
```


Run 
```shell
$ rspec-sinatra init --app  MyApp lib/my_app.rb
```
And
```
$ rspec --init
``` 
Also, edit the `.rspec` file and add `--format documentation` to see a more verbose rspec output. 
Create a Gemfile: `touch Gemfile` and add some basic libraries you will be using: 
```
source 'https://rubygems.org'

gem 'sinatra'

group :development, :test do
  gem 'capybara'
  gem 'launchy'
  gem 'rspec'
  gem 'rspec-sinatra'
  gem 'shotgun'
end
```
add `gem 'rack-test'` to your Gemfile and `require` it on top of your `spec/spec_helper.rb`. 

Also add `config.include Rack::Test::Methods` to your Rspec.configure block.
create a `features` folder in `spec` 
```
mkdir spec/features
``` 
create a `my_app_spec.rb` in the `features` folder. 
Add your first test:
```ruby
    #
```

In order to get the assets to load, modify your `config.ru` to include:
```
use Rack::Static, urls: ['/css', '/js', '/images', '/fonts'], root: 'assets'
```
And create the folders. 
```shell
$ mkdir assets
$ mkdir assets/css
$ mkdir assets/js
$ mkdir assets/images
$ mkdir assets/fonts
```

Also, you are going to need a layout file in your `views` folder
```shell
$ mkdir lib/vievs/layout.erb

```
[Not be continued...]



