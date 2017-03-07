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

setImmediate( async() => {
    const alarms = await Rest.alarms.summary();
    fs.writeFileSync('./alarms.json',JSON.stringify(alarms,null,4));
    console.log('done');
});
```
