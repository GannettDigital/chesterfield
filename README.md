# Chesterfield

[![npm version](https://badge.fury.io/js/chesterfield.svg)](https://badge.fury.io/js/chesterfield)
[![Build Status](https://travis-ci.org/GannettDigital/chesterfield.svg)](https://travis-ci.org/GannettDigital/chesterfield)
[![Coverage Status](https://coveralls.io/repos/github/GannettDigital/chesterfield/badge.svg)](https://coveralls.io/github/GannettDigital/chesterfield)

Chesterfield is wrapper for the Node JS Couchbase SDK for writing Functional Javascript.

## Installation
```Node
npm install chesterfield --save
```

## Running Tests
```bash
git clone https://github.com/GannettDigital/chesterfield.git
cd chesterfield
npm test
```

## Example
```Node
var cb = require('chesterfield');

var cluster = cb.cluster('couchbase://address2couchbase');
var bucket = cb.open(cluster, 'bucket_name', 'password');

var popeMobile = {
    id: 9000,
    type: 'miracle whip'
};

var popeMobileKey = 'vehicle_' + popeMobile.id;

cb.upsert(bucket, popeMobileKey, popeMobile, function(error, result) {
    cb.get(bucket, popeMobileKey, function(error, result) {
        console.log(JSON.stringify(result.value));
    });
});

```

## Contributing

Please see ```CONTRIBUTING.md``` for more details on contributing to the repository.
