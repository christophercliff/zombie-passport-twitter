## Installation

```
$ npm install zombie-passport-twitter
```

## Usage

```js
var zpt = require('zombie-passport-twitter')

zpt.signIn({
    url: '/auth/twitter',
    username: YOUR_USERNAME,
    password: YOUR_PASSWORD,
    wait: 5e3
}, function(err, browser){
    // you're signed in!
})
```

You can use the session to sign additional requests, using [`supertest`](https://github.com/visionmedia/supertest) for example:

```js
zpt.signIn(YOUR_OPTIONS, function(err, browser){
    supertest(YOUR_SERVER)
        .get('/')
        .set('cookie', browser.cookies[0].toString())
        .expect(200)
})
```
