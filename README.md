Heroku buildpack: geos
======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
vendors the geos library. 

Based on: https://github.com/heroku/heroku-geo-buildpack.git

> NOTE: Currently supports version 3.8.1 for the Heroku-18 stack only.

Usage
-----

Example usage:

```
$ heroku buildpacks:set https://github.com/MonkeyTech/heroku-geos-buildpack.git
$ heroku buildpacks:add heroku/ruby
```

Run `heroku buildpacks` to make sure that `heroku-geos-buildpack` is added before
the language buildpacks.

```
$ heroku buildpacks
=== sushi Buildpack URLs
1. https://github.com/MonkeyTech/heroku-geos-buildpack.git
2. heroku/ruby
```

Testing
-------

For rgeo:

```ruby
>>> require 'rgeo'
>>> RGeo::Geos.supported?
=> true
```