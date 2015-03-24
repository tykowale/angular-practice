#Angular Presentation

Angular and rails can go hand in hand for a project. Both of these are very special in that they require a lot of configuration to get started.So start off with build a new rails app and well make our configurations as we go.
Rails does not manage front end dependencies and out Gemfile can only do so much. So before we move on lets install Bower. It was created by Twitter for exact reason, think of it as a Gemfile for your front end needs.

```
$ brew install npm
$ npm install -g bower
```

We will get back to Bower in a bit but first install our accompanying gem.

```
gem 'bower-rails'
```

Bundle install now, and you can see that bower now has a bunch of rake tasks. Run ```be rake bower:install``` to get a nice set of beginner tools to use with bower.

Good news everyone, more configuration! Bower is not stock within rails so add the following lines to your config/application.rb

```
config.assets.paths << Rails.root.join("vendor","assets","bower_components")
  config.assets.paths << Rails.root.join("vendor","assets","bower_components","bootstrap-sass-official","assets","fonts")
config.assets.precompile << %r(.*.(?:eot|svg|ttf|woff)$)
```

We're getting close to the finish line! Add the following lines to your application.js and application.css and we should be ready to rock 'n' roll

```
application.js

//= require angular/angular
---------------------------
application.css

@import "bootstrap-sass-official/assets/stylesheets/bootstrap-sprockets";
@import "bootstrap-sass-official/assets/stylesheets/bootstrap";
```

Congrats! You just finished the set up and we should be ready to start creating angular magic!

Create a home controller and make a route leading towards it for the simplest angular app ever.
