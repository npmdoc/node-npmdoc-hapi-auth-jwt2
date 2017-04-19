# npmdoc-hapi-auth-jwt2

#### api documentation for  [hapi-auth-jwt2 (v7.2.4)](https://github.com/dwyl/hapi-auth-jwt2)  [![npm package](https://img.shields.io/npm/v/npmdoc-hapi-auth-jwt2.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-hapi-auth-jwt2) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-hapi-auth-jwt2.svg)](https://travis-ci.org/npmdoc/node-npmdoc-hapi-auth-jwt2)

#### Hapi.js Authentication Plugin/Scheme using JSON Web Tokens (JWT)

[![NPM](https://nodei.co/npm/hapi-auth-jwt2.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/hapi-auth-jwt2)

- [https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-hapi-auth-jwt2/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "@nelsonic",
        "url": "https://github.com/nelsonic"
    },
    "bugs": {
        "url": "https://github.com/dwyl/hapi-auth-jwt2/issues"
    },
    "contributors": [
        {
            "name": "Kevin Wu"
        },
        {
            "name": "Alan Shaw"
        },
        {
            "name": "Benjamin Lees"
        },
        {
            "name": "Jason Nah"
        },
        {
            "name": "Steven Gangstead"
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
            "name": "nelsonic"
        }
    ],
    "name": "hapi-auth-jwt2",
    "optionalDependencies": {},
    "pre-commit": [
        "coverage",
        "jshint"
    ],
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



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
