# Chapter 2
## Mostly static pages
### 3.1 Sample app setup
no notes
### 3.2 Static pages
no notes
### 3.2.1 Generated static pages
In Rails, this can be accomplished with `rails destroy` followed by the name of the generated element. In particular, these two commands cancel each other out:
```
  $ rails generate controller StaticPages home help
  $ rails destroy  controller StaticPages home help
```
Similarly, in Chapter 6 we’ll generate a model as follows:

`$ rails generate model User name:string email:string`

This can be undone using

`$ rails destroy model User`

Another technique related to models involves undoing migrations, which we saw briefly in Chapter 2 and will see much more of starting in Chapter 6. Migrations change the state of the database using the command

`$ rails db:migrate`
We can undo a single migration step using

`$ rails db:rollback`

To go all the way back to the beginning, we can use

`$ rails db:migrate VERSION=0`

As you might guess, substituting any other number for 0 migrates to that version number, where the version numbers come from listing the migrations sequentially.

In the case of the Static Pages controller, both of its methods are initially empty:

```
def home
end

def help
end
```

In plain Ruby, these methods would simply do nothing. In Rails, the situation is different—`StaticPagesController` is a Ruby class, but because it inherits from `ApplicationController` the behavior of its methods is specific to Rails: **when visiting the URL /static_pages/home, Rails looks in the Static Pages controller and executes the code in the home action, and then renders the view (the V in MVC) corresponding to the action. In the present case, the home action is empty, so all visiting /static_pages/home does is render the view.** So, what does a view look like, and how do we find it?

### 3.3 Getting started with testing
no notes
### 3.3.1 Our first test

```
test "should get home" do
  get static_pages_home_url
  assert_response :success
end
```
The above test says “Let’s test the Home page by issuing a GET request to the Static Pages home URL and then making sure we receive a ‘success’ status code in response.”

### 3.4 Slightly dynamic pages
`assert_select` method lets us test for the presence of a particular HTML tag (sometimes called a “selector”, hence the name):

`assert_select "title", "Home | Ruby on Rails Tutorial Sample App"`

In particular, the code above checks for the presence of a <title> tag containing the string “Home | Ruby on Rails Tutorial Sample App”

### 3.4.4 Setting the root route
