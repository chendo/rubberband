
# RubberBand
[![Build Status](https://secure.travis-ci.org/grantr/rubberband.png?branch=master)](http://travis-ci.org/grantr/rubberband)

An ElasticSearch client with ThriftClient-like failover handling.

## License

Copyright 2010-2012 Grant Rodgers. See included LICENSE file.

## Features

* Automatic failover, retry, and peer discovery
* Support for multiple transports (HTTP, Thrift, Memcached TODO)
* Support for multiple encodings (JSON (Yajl), Smile TODO)

## Supported Rubies

Tested on 1.8.7, 1.9.2, 1.9.3, and Rubinius in 1.8 and 1.9 mode.

## Usage

Instantiate a client:

    client = ElasticSearch.new('127.0.0.1:9200', :index => "twitter", :type => "tweet")

Instantiate a client with multiple servers:
  
    client = ElasticSearch.new(['127.0.0.1:9200', '127.0.0.1:9201'])

Instantiate a client using a Heroku URL (this sets the default index):

    client = ElasticSearch.new(ENV['ELASTICSEARCH_URL'])

API:

  client.index({:body => "elasticsearch is cool"}, :id => 1)
  client.get("1")
  client.search("body:elasticsearch")

## TODO

See TODO file.

## Contributing

http://github.com/grantr/rubberband

Fork, code, send pull request
