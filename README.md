# api documentation for  [hapi-auth-jwt2 (v7.2.4)](https://github.com/dwyl/hapi-auth-jwt2)  [![npm package](https://img.shields.io/npm/v/npmdoc-hapi-auth-jwt2.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-hapi-auth-jwt2) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-hapi-auth-jwt2.svg)](https://travis-ci.org/npmdoc/node-npmdoc-hapi-auth-jwt2)
#### Hapi.js Authentication Plugin/Scheme using JSON Web Tokens (JWT)

[![NPM](https://nodei.co/npm/hapi-auth-jwt2.png?downloads=true)](https://www.npmjs.com/package/hapi-auth-jwt2)

[![apidoc](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-hapi-auth-jwt2_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "@nelsonic",
        "email": "contact.nelsonic@gmail.com",
        "url": "https://github.com/nelsonic"
    },
    "bugs": {
        "url": "https://github.com/dwyl/hapi-auth-jwt2/issues"
    },
    "contributors": [
        {
            "name": "Kevin Wu",
            "email": "@eventhough <kevindwusf@gmail.com"
        },
        {
            "name": "Alan Shaw",
            "email": "@alanshaw <alan@tableflip.io"
        },
        {
            "name": "Benjamin Lees",
            "email": "@benjaminlees <benji.man.lees@gmail.com"
        },
        {
            "name": "Jason Nah",
            "email": "@jyn <jason.@gmail.com"
        },
        {
            "name": "Steven Gangstead",
            "email": "@gangstead <steven@gangstead.com"
        }
    ],
    "dependencies": {
        "boom": "^4.0.0",
        "cookie": "^0.3.1",
        "jsonwebtoken": "^7.1.9"
    },
    "description": "Hapi.js Authentication Plugin/Scheme using JSON Web Tokens (JWT)",
    "devDependencies": {
        "aguid": "^1.0.4",
        "goodparts": "^1.2.0",
        "hapi": "^16.0.1",
        "istanbul": "^0.4.5",
        "jshint": "^2.9.3",
        "pre-commit": "^1.1.3",
        "tap-spec": "^4.1.1",
        "tape": "^4.6.0"
    },
    "directories": {},
    "dist": {
        "shasum": "5d77f63bafacda7a381aefe855f1683bc8641081",
        "tarball": "https://registry.npmjs.org/hapi-auth-jwt2/-/hapi-auth-jwt2-7.2.4.tgz"
    },
    "engines": {
        "node": ">=4.2.3"
    },
    "gitHead": "fa5b3be18979c75307f0706a8976f352955af0eb",
    "homepage": "https://github.com/dwyl/hapi-auth-jwt2",
    "keywords": [
        "Hapi.js",
        "Authentication",
        "Auth",
        "JSON Web Tokens",
        "JWT"
    ],
    "license": "ISC",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "nelsonic",
            "email": "contact.nelsonic@gmail.com"
        }
    ],
    "name": "hapi-auth-jwt2",
    "optionalDependencies": {},
    "pre-commit": [
        "coverage",
        "jshint"
    ],
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/dwyl/hapi-auth-jwt2.git"
    },
    "scripts": {
        "coverage": "istanbul cover ./node_modules/tape/bin/tape ./test/*.test.js && istanbul check-coverage --statements 100 --functions 100 --lines 100 --branches 100",
        "jshint": "./node_modules/jshint/bin/jshint -c .jshintrc --exclude-path .gitignore .",
        "lint": "goodparts lib",
        "quick": "./node_modules/tape/bin/tape ./test/*.test.js | node_modules/tap-spec/bin/cmd.js",
        "report": "open coverage/lcov-report/index.html",
        "start": "node example/server.js",
        "test": "istanbul cover ./node_modules/tape/bin/tape ./test/*.test.js  | node_modules/tap-spec/bin/cmd.js"
    },
    "version": "7.2.4"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module hapi-auth-jwt2](#apidoc.module.hapi-auth-jwt2)
1.  [function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>extract (request, options)](#apidoc.element.hapi-auth-jwt2.extract)
1.  [function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>register (server, options, next)](#apidoc.element.hapi-auth-jwt2.register)

#### [module hapi-auth-jwt2.extract](#apidoc.module.hapi-auth-jwt2.extract)
1.  [function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>extract (request, options)](#apidoc.element.hapi-auth-jwt2.extract.extract)
1.  [function <span class="apidocSignatureSpan">hapi-auth-jwt2.extract.</span>isValid (token)](#apidoc.element.hapi-auth-jwt2.extract.isValid)



# <a name="apidoc.module.hapi-auth-jwt2"></a>[module hapi-auth-jwt2](#apidoc.module.hapi-auth-jwt2)

#### <a name="apidoc.element.hapi-auth-jwt2.extract"></a>[function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>extract (request, options)](#apidoc.element.hapi-auth-jwt2.extract)
- description and source-code
```javascript
function extract(request, options) {
  // The key holding token value in url or cookie defaults to token
  var auth, token;
  var cookieKey = customOrDefaultKey(options, 'cookieKey', 'token');
  var headerKey = customOrDefaultKey(options, 'headerKey', 'authorization');
  var urlKey = customOrDefaultKey(options, 'urlKey', 'token');
  var pattern = new RegExp(options.tokenType + '\\s+([^$]+)', 'i');

  if (urlKey && request.query[urlKey]) { // tokens via url: https://github.com/dwyl/hapi-auth-jwt2/issues/19
    auth = request.query[urlKey];
  } else if (headerKey && request.headers[headerKey]) {
    if (typeof options.tokenType === 'string') {
      token = request.headers[headerKey].match(pattern);
      auth = token === null ? null : token[1];
    } else {
      auth = request.headers[headerKey];
    } // JWT tokens in cookie: https://github.com/dwyl/hapi-auth-jwt2/issues/55
  } else if (cookieKey && request.headers.cookie) {
    auth = Cookie.parse(request.headers.cookie)[cookieKey];
  }

  // strip pointless "Bearer " label & any whitespace > http://git.io/xP4F
  return auth ? auth.replace(/Bearer/gi, '').replace(/ /g, '') : null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.hapi-auth-jwt2.register"></a>[function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>register (server, options, next)](#apidoc.element.hapi-auth-jwt2.register)
- description and source-code
```javascript
register = function (server, options, next) {
  server.auth.scheme('jwt', internals.implementation); // hapijs.com/api#serverauthapi

  return next();
}
```
- example usage
```shell
...
  return callback(null, true);
}
};

var server = new Hapi.Server();
server.connection({ port: 8000 });
    // include our module here ↓↓
server.register(require('hapi-auth-jwt2'), function (err) {

if(err){
  console.log(err);
}

server.auth.strategy('jwt', 'jwt',
{ key: 'NeverShareYourSecret',          // Never Share your secret key
...
```



# <a name="apidoc.module.hapi-auth-jwt2.extract"></a>[module hapi-auth-jwt2.extract](#apidoc.module.hapi-auth-jwt2.extract)

#### <a name="apidoc.element.hapi-auth-jwt2.extract.extract"></a>[function <span class="apidocSignatureSpan">hapi-auth-jwt2.</span>extract (request, options)](#apidoc.element.hapi-auth-jwt2.extract.extract)
- description and source-code
```javascript
function extract(request, options) {
  // The key holding token value in url or cookie defaults to token
  var auth, token;
  var cookieKey = customOrDefaultKey(options, 'cookieKey', 'token');
  var headerKey = customOrDefaultKey(options, 'headerKey', 'authorization');
  var urlKey = customOrDefaultKey(options, 'urlKey', 'token');
  var pattern = new RegExp(options.tokenType + '\\s+([^$]+)', 'i');

  if (urlKey && request.query[urlKey]) { // tokens via url: https://github.com/dwyl/hapi-auth-jwt2/issues/19
    auth = request.query[urlKey];
  } else if (headerKey && request.headers[headerKey]) {
    if (typeof options.tokenType === 'string') {
      token = request.headers[headerKey].match(pattern);
      auth = token === null ? null : token[1];
    } else {
      auth = request.headers[headerKey];
    } // JWT tokens in cookie: https://github.com/dwyl/hapi-auth-jwt2/issues/55
  } else if (cookieKey && request.headers.cookie) {
    auth = Cookie.parse(request.headers.cookie)[cookieKey];
  }

  // strip pointless "Bearer " label & any whitespace > http://git.io/xP4F
  return auth ? auth.replace(/Bearer/gi, '').replace(/ /g, '') : null;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.hapi-auth-jwt2.extract.isValid"></a>[function <span class="apidocSignatureSpan">hapi-auth-jwt2.extract.</span>isValid (token)](#apidoc.element.hapi-auth-jwt2.extract.isValid)
- description and source-code
```javascript
function isValid(token) {
  return token.split('.').length === 3;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
