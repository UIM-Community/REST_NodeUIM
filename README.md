# REST_NodeUIM
NodeJS RESTFul lib for CA UIM

This lib is just an example on how to achieve RESTFul with NodeJS for CA UIM.

## Requirement

- NodeJS 7.6.0 or higher.

## Examples 

```js
'use strict';

const lib = require('./lib');
const fs  = require('fs');

const Rest = new lib.REST({
    hostname: "portail-url.com",
    user: "administrator",
    password: "password"
});

setImmediate( async() => {
    const alarms = await Rest.alarms.summary();
    fs.writeFileSync('./alarms.json',JSON.stringify(alarms,null,4));
    console.log('done');
});
```
