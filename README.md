# Ghost mongodb storage

Custom storage module for [Ghost blogging platform] (https://ghost.org/) that allows to store images in mongodb instead of local file system,
helpful i.e. when hosting ghost blog on heroku.
Based on ghost 0.6.4.

Does not make use of GridFS - if your image sizes exceed 16MB you cannot use this module.

## Installation

    npm install --save ghost-mongodb-storage

## Create storage module

Create index.js file with folder path 'content/storage/ghost-mongodb/index.js'

    'use strict';
    module.exports = require('ghost-mongodb-storage');

## Configuration

Add `storage` block to file `config.js` in each environment as below:


     storage: {
        active: 'ghost-mongodb',
        'ghost-mongodb': {
            mongodbUrl: 'mongodb://<user>:<password>@<mongohost>:<port>/<dbname>'
        }
    },


Example URL using mongolab:

    mongodb://myuser:mypassword@ds055662.mongolab.com:55772/heroku_lk5qqg4j


### License:
Licensed under the Apache License, Version 2.0, see http://www.apache.org/licenses/LICENSE-2.0


