# Chapter 2
## A toy app
no notes
### 2.1 Planning the application
Now we’re ready to start making the app itself. The typical first step when making a web application is to create a data model, which is a representation of the structures needed by our application. In our case, the toy app will be a Twitter-style microblog, with only *users* and short (micro)posts. Thus, we’ll begin with a model for users of the app, and then we’ll add a model for *microposts*.

### 2.1.1 A toy model for users
Users of our toy app will have a unique identifier called *id* (of type integer), a publicly viewable *name* (of type string), and an *email address* (also of type string) that will double as a unique username.

### 2.1.2 A toy model for microposts
The core of the *micropost* data model is even simpler than the one for *users*: a *micropost* has only an *id* and a *content* field for the micropost’s text (of type text). There’s an additional complication, though: we want to associate each *micropost* with a particular *user*. We’ll accomplish this by recording the *user_id* of the owner of the post.

### 2.2 The Users resource
```
$ rails generate scaffold User name:string email:string
      invoke  active_record
      create    db/migrate/20160515001017_create_users.rb
      create    app/models/user.rb
      invoke    test_unit
      create      test/models/user_test.rb
      create      test/fixtures/users.yml
      invoke  resource_route
       route    resources :users
      invoke  scaffold_controller
      create    app/controllers/users_controller.rb
      invoke    erb
      create      app/views/users
      create      app/views/users/index.html.erb
      create      app/views/users/edit.html.erb
      create      app/views/users/show.html.erb
      create      app/views/users/new.html.erb
      create      app/views/users/_form.html.erb
      invoke    test_unit
      create      test/controllers/users_controller_test.rb
      invoke    helper
      create      app/helpers/users_helper.rb
      invoke      test_unit
      invoke    jbuilder
      create      app/views/users/index.json.jbuilder
      create      app/views/users/show.json.jbuilder
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/users.coffee
      invoke    scss
      create      app/assets/stylesheets/users.scss
      invoke  scss
      create    app/assets/stylesheets/scaffolds.scss
```

By including `name:string` and `email:string`, we have arranged for the User model to have its intended form. **(Note that there is no need to include a parameter for id; it is created automatically by Rails for use as the *primary key* in the database.)**

To proceed with the toy application, we first need to migrate the database using `rails db:migrate`

###2.2.1 A user tour
no notes

###2.2.2 MVC in action
