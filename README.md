# REST_NodeUIM
NodeJS RESTFul lib for CA UIM

## Examples 

```js
'use strict';

const lib = require('./lib');
const fs  = require('fs');

const Rest = new lib.REST({
    hostname: "portail-ca.com",
    user: "administrator",
    password: "password"
});

const res = Rest.alarms.summary().then( body => {
    fs.writeFileSync('./alarms.json',JSON.stringify(body,null,4));
    console.log('done');
});
```
