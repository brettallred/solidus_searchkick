Solidus + Searchkick
===============

Add [Elasticsearch](http://elastic.co) goodies to Spree, powered by [searchkick](http://searchkick.org)

Features
--------

* Full search (keyword, in_taxon)
* Taxons Aggregations (aggs)
* Search Autocomplete ([Typeahead](https://twitter.github.io/typeahead.js/))
* Added `/best` route, where best selling products are boosted in first page


Installation
------------

Add searchkick and solidus_searchkick to your Gemfile:

```ruby
gem 'searchkick'
gem 'solidus_searchkick'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g solidus_searchkick:install

OR

rake solidus_searchkick:install:migrations
```

[Install elasticsearch](https://www.elastic.co/downloads/elasticsearch)

Documentation
-------------

By default, only the `Spree::Product` class is indexed and to control what data is indexed, override `Spree::Product#search_data` method. Call `Spree::Product.reindex` after changing this method.

To enable or disable taxons filters, go to taxonomy form and change `filterable` boolean.

Testing
-------

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'solidus_searchkick/factories'
```

Copyright (c) 2016 Jim Smith, released under the New BSD License