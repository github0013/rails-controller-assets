# RailsControllerAssets

[![Build Status](https://travis-ci.org/pusewicz/rails-controller-assets.png?branch=master)](https://travis-ci.org/pusewicz/rails-controller-assets)
[![Code Climate](https://codeclimate.com/github/pusewicz/rails-controller-assets.png)](https://codeclimate.com/github/pusewicz/rails-controller-assets)

This gems allows to automatically precompile bundles of assets per controller or controller/action pair.

It's great when you want to keep action or controller specific CSS/JavaScript in a separate file.

## Usage

In your Gemfile:

```ruby
gem 'rails-controller-assets'
```

Create new bundle files (eg. like application.css) for a `PostsController`:

In `app/assets/stylesheets/posts.css`:

```css
.post-title { color: red }
```

In your application layout add to your stylesheets definition:

```erb
<%= stylesheets_link_tag 'application', *controller_stylesheets %>
<%= javascript_include_tag 'application', *controller_javascripts %>
```

And that's it!

The gem will look for bundle files that match:

* `{controller_name}.{js|css}`
* `{controller_name}_{action_name}.{js|css}`


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/pusewicz/rails-controller-assets/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

