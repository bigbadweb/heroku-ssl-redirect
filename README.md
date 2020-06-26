# SSL Redirect for Heroku


Usage

`npm install --save @bigbadweb/heroku-ssl-redirect`


Use the `NODE_ENV` environment variable. 

```
const express = require('express');
const sslredirect = require('heroku-ssl-redirect')

var app = express();
// A list of environments in which to test for SSL being used. This uses process.env.NODE_ENV. 

const doDedirectForTheseNodeEnvs = ['production', 'staging', 'heroku'];

// 301 - Permanent Redirect or 302 - Temporary Redirect (default)
const redirectType = 302; 

app.use(sslredirect(doDedirectForTheseNodeEnvs, redirectType));
```