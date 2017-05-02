# Chapter 1
## From zero to deploy
### 1.1 Introduction
no notes
### 1.2 Up and running
no notes
### 1.2.1 Development environment
Setting up a Rails development environment can be challenging, so I recommend the [Cloud IDE](https://c9.io/) for most readers. For those who want to go the local route, try the steps at [Install Rails](https://installRails.com), and be prepared for a challenging exercise in technical sophistication.
### 1.2.2 Installing Rails
To install Rails, we’ll use the gem command provided by the RubyGems package manager, which involves typing the command shown below: `$ gem install rails -v 5.0.1`

Here the `-v`flag ensures that the specified version of Rails gets installed, which is important for getting results consistent with this tutorial. In this case, version `5.0.1` has been installed.

### 1.3 The first application
Virtually all Rails applications start the same way, by running the `rails new` command. This handy command creates a skeleton Rails application in a directory of your choice.

```
$ cd                  # Change to the home directory.
$ mkdir workspace     # Make a workspace directory.
$ cd workspace/       # Change into the workspace directory.
```
**A crash course on Unix commands**

| Description   |      Command      |  Example |
|----------|:----------:|------:|
| list contents |  ls | $ ls -l|
| make directory	 |  mkdir < dirname >	   |  $ mkdir workspace |
| change directory | cd < dirname > |    $ cd workspace/ |
| cd one directory up | |    $ cd .. |
| cd to home directory | |   $ cd |
| move file (rename) | mv < source >< target > | $ mv foo bar |
| remove file | rm < file > | $ rm foo |
| remove empty directory | rmdir < directory > | $ rmdir workspace/ |
| remove nonempty directory | rm -rf < directory > | $ rm -rf tmp/ |

```
$ cd ~/workspace
$ rails _5.0.1_ new hello_app
      create
      create  README.md
      create  Rakefile
      create  config.ru
      create  .gitignore
      create  Gemfile
      create  app
      create  app/assets/config/manifest.js
      create  app/assets/javascripts/application.js
      create  app/assets/javascripts/cable.js
      create  app/assets/stylesheets/application.css
      create  app/channels/application_cable/channel.rb
      create  app/channels/application_cable/connection.rb
      create  app/controllers/application_controller.rb
      .
      .
      .
      create  tmp/cache/assets
      create  vendor/assets/javascripts
      create  vendor/assets/javascripts/.keep
      create  vendor/assets/stylesheets
      create  vendor/assets/stylesheets/.keep
      remove  config/initializers/cors.rb
         run  bundle install
Fetching gem metadata from https://rubygems.org/..........
Fetching additional metadata from https://rubygems.org/..
Resolving dependencies...
Installing rake 11.1.2
Using concurrent-ruby 1.0.2
.
.
.
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted
```


This standard directory and file structure is one of the many advantages of Rails: it immediately gets you from zero to a functional (if minimal) application. Moreover, since the structure is common to all Rails apps, you can immediately get your bearings when looking at someone else’s code.

**Unless you specify a version number to the gem command, Bundler will automatically install the latest requested version of the gem.** This is the case, for example: `gem 'sqlite3'`

`gem 'uglifier', '>= 1.3.0'` installs the latest version of the uglifier gem (which handles file compression for the asset pipeline) **as long as it’s greater than or equal to version 1.3.0—even if it’s, say, version 7.2.**

`gem 'coffee-rails', '~> 4.0.0'` installs the gem coffee-rails as long as it’s newer than version 4.0.0 and not newer than 4.1. **In other words, the >= notation always installs the latest gem, whereas the ~> 4.0.0 notation only installs updated gems where the last digit differs (e.g., from 4.0.0 to 4.0.1), but the digits before that releases (e.g., from 4.0 to 4.1).**

### 1.3 Model-View-Controller (MVC)

Rails follows the **model-view-controller (MVC)** architectural pattern, which enforces a **separation between the data in the application (such as user information)** and the **code used to display it**, which is a common way of structuring a graphical user interface (GUI).

### 1.4 Version control with Git

**First time system setup**

After installing Git, you should perform a couple of one-time setup steps. These are system setups, meaning you only have to do them once per computer:

```
$ git config --global user.name "Your Name"
$ git config --global user.email your.email@example.com
```

### 1.5 Deploying
no notes
### 1.5.1 Heroku setup
Heroku uses the PostgreSQL database (pronounced “post-gres-cue-ell”, and often called “Postgres” for short), which means that we need to add the pg gem in the production environment to allow Rails to talk to Postgres:

```
group :production do
  gem 'pg', '0.18.4'
end
```



# Chapter 2
## A toy app
