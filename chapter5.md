# Chapter 5
## Filling in the layout
### 5.1 Adding some structure

### Listing 5.4: Downloading a cat picture from the Internet
`$ curl -OL cdn.learnenough.com/kitten.jpg`

In the Rails Tutorial, we’ll follow the common convention of using the `path` form except when doing redirects, where we’ll use the `url` form. (This is because the HTTP standard technically requires a full URL after redirects, though in most browsers it will work either way.)

```
help_path -> '/help'
help_url  -> 'http://www.example.com/help'
```

we can simulate the same series of steps using an integration test, which allows us to write an end-to-end test of our application’s behavior. We can get started by generating a template test, which we’ll call site_layout:

```
$ rails generate integration_test site_layout
      invoke  test_unit
      create    test/integration/site_layout_test.rb
```
