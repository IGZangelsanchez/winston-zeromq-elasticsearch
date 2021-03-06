winston-zeromq-elasticsearch
============================

A [ZeroMQ-ElasticSearch](https://github.com/bpaquet/transport-zeromq) transport for [Winston](https://github.com/flatiron/winston). Sends the messages to save using a [ZeroMQ](http://zeromq.org/) PUSH socket. The message format is compatible with [LogStash](http://logstash.net/).

## Installation

### Installing winston-zeromq-elasticsearch

```bash
 $ npm install winston
 $ npm install winston-zeromq-elasticsearch
```

## Usage

### Options

This winston transport takes the following options:
 - __socketAddress__: The ZeroMQ socket address you want to send to.
 - __level__: Level of messages that this transport should log. (default 'debug')
 - __silent__: Boolean flag indicating whether to suppress output. (default false)
 - __metadata__: Default metadata to be added on each log entry. (default {})

### Using the Default Logger

```js
var winston = require('winston');

//
// Requiring `winston-zeromq-elasticsearch` will expose 
// `winston.transports.ZeroMQElasticSearch`
//
require('winston-zeromq-elasticsearch').ZeroMQElasticSearch;

winston.add(winston.transports.ZeroMQElasticSearch,
    { socketAddress: 'tcp://0.0.0.0:9700' });

winston.info('Hello world!');

```


### Using your own Logger

```js
var winston = require('winston');

//
// Requiring `winston-zeromq-elasticsearch` will expose 
// `winston.transports.ZeroMQElasticSearch`
//
require('winston-zeromq-elasticsearch').ZeroMQElasticSearch;

var logger = new winston.Logger ({
  transports : [
    new winston.transports.ZeroMQElasticSearch({
      socketAddress : 'tcp://0.0.0.0:9700'
    })
  ]
});

logger.info('Hello world!');

```


## Environment

- [ZeroMQ](http://zeromq.org/)
- [Java bindings for ZeroMQ](http://zeromq.org/bindings:java)
- [Elastic search](http://www.elasticsearch.org/download/)
- [Transport for ZeroMQ in Elastic search](https://github.com/bpaquet/transport-zeromq)

You can manage the saved logs using [Kibana](http://www.elasticsearch.org/overview/kibana/installation/)


#### Author: [Angel Sanchez](http://www.thegameofcode.com/)

#### License: MIT
