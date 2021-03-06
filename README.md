[![Gem Version](https://badge.fury.io/rb/blogit.png)](http://badge.fury.io/rb/blogit)
[![Code Climate](https://codeclimate.com/github/KatanaCode/blogit.png)](http://codeclimate.com/github/KatanaCode/blogit/)
[![Blogit](https://gemnasium.com/KatanaCode/blogit.png)](https://gemnasium.com/KatanaCode/blogit)
[![Travis CI](https://travis-ci.org/KatanaCode/blogit.png)](https://travis-ci.org/KatanaCode/blogit.png)



# Blogit (beta)

Blogit is a flexible blogging solution for Rails apps. It:

* Is Rack based;
* Is a complete MVC solution based on Rails engines
* Aims to work right out of the box but remain fully customisable.

## Installation

Add this to your Gemfile

``` ruby
gem "blogit"
```

...and run `bundle install` to install the gem.

Next, run:

``` bash
# add an initializer to config/initializers with all of the configuration options
$ rails g blogit:install
# This will add the necessary migrations to your app's db/migrate directory
rake blogit:install:migrations
# This will run any pending migrations
rake db:migrate
``` 
then add the following to your routes.rb file:

``` bash
# config/routes.rb
mount Blogit::Engine => "/blog"
```

Define `ApplicationController#current_user` and `ApplicationController#login_required` methods if your app doesn't already have these.

... and finally, declare which of your models acts as blogger in your app (usually User).

``` ruby
class User
  
  blogs

end
```  

## Configuration

Running `rails g blogit:install` will add an initializer file named blogit.rb. In here
you can set various configuration options. Please [read the documentation](http://rubydoc.info/gems/blogit/Blogit/Configuration) for a full list of the options available.

## At no extra cost...

we'll also throw in:

* An XML Sitemap located at `/blog/posts.xml`
* An RSS feed located at `/blog/posts.rss`
* Sitemap submission to the major search engines (via [Pingr](http://github.com/katanacode/pingr "Pingr") - off by default)
* Page Caching and Sweeping
* Internationalization (see the [locales file](config/locales/en.yml) for configurable options)
* Share links (Google+, Twitter & Facebook)
* [Disquss Comments](http://disqus.com)
* Code Syntax Highlighting CSS file (add `*= require pygments` to your app's stylesheet)

## Rails 4

@grncdr Has contributed changes for Rails 4 compatibility. Check out the rails 4 branch for more info. NOTE - This code hasn't been tested yet and may contain bugs.

## Issues

If you discover a problem with Blogit, please let us know about it. 

**Remember** to search the [issues list](https://github.com/KatanaCode/blogit/issues) first in case your issue has already been raised
by another Githuber

## Documentation

Full documentation is available here: http://rubydoc.info/gems/blogit

## Contributing

You're welcome to contribute to Blogit. Please consult the [contribution guidelines](https://github.com/KatanaCode/blogit/wiki/Contributing) for more info.

## Legal Stuff

Copyright 2011 [Katana Code Ltd.](http://katanacode.com)

See [LEGAL](LEGAL) for full details.

## Credits

Developed by [Katana Code](http://katanacode.com)

with generous contributions from:

* [Philou](https://github.com/philou)
* [Stewart McKee](https://github.com/stewartmckee)
* [Karsten Silkenbäumer](https://github.com/kassi)

## About Katana Code

Katana Code are [web developers based in Edinburgh, Scotland](http://katanacode.com/ "Katana Code").
