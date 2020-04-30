Heroku buildpack: geos
======================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
vendors the geos library.

You will use this buildpack with other major buildpack such as Ruby buildpack.

Based on: https://github.com/cyberdelia/heroku-geo-buildpack

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
>>> RGeo::CoordSys::Proj4.supported?
=> true
>>> RGeo::Geos.supported?
=> true
```