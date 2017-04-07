# api documentation for  [md5-file (v3.1.1)](https://github.com/roryrjb/md5-file#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-md5-file.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-md5-file) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-md5-file.svg)](https://travis-ci.org/npmdoc/node-npmdoc-md5-file)
#### return an md5sum of a given file

[![NPM](https://nodei.co/npm/md5-file.png?downloads=true)](https://www.npmjs.com/package/md5-file)

[![apidoc](https://npmdoc.github.io/node-npmdoc-md5-file/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-md5-file_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-md5-file/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-md5-file/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-md5-file/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Rory Bradford",
        "email": "roryrjb@gmail.com",
        "url": "www.roryrjb.com"
    },
    "bugs": {
        "url": "https://github.com/roryrjb/md5-file/issues"
    },
    "dependencies": {},
    "description": "return an md5sum of a given file",
    "devDependencies": {
        "mocha": "^2.4.5",
        "standard": "^7.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "db3c92c09bbda5c2de883fa5490dd711fddbbab9",
        "tarball": "https://registry.npmjs.org/md5-file/-/md5-file-3.1.1.tgz"
    },
    "files": [
        "index.js",
        "promise.js"
    ],
    "gitHead": "ca5cb2c4d8438d2a45bb342235fec9f7016a2364",
    "homepage": "https://github.com/roryrjb/md5-file#readme",
    "keywords": [
        "md5",
        "md5sum",
        "checksum"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "linusu",
            "email": "linus@folkdatorn.se"
        },
        {
            "name": "roryrjb",
            "email": "roryrjb@gmail.com"
        }
    ],
    "name": "md5-file",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/roryrjb/md5-file.git"
    },
    "scripts": {
        "test": "standard && mocha"
    },
    "version": "3.1.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module md5-file](#apidoc.module.md5-file)
1.  [function <span class="apidocSignatureSpan">md5-file.</span>promise (filename)](#apidoc.element.md5-file.promise)
1.  [function <span class="apidocSignatureSpan">md5-file.</span>sync (filename)](#apidoc.element.md5-file.sync)

#### [module md5-file.promise](#apidoc.module.md5-file.promise)
1.  [function <span class="apidocSignatureSpan">md5-file.</span>promise (filename)](#apidoc.element.md5-file.promise.promise)
1.  [function <span class="apidocSignatureSpan">md5-file.promise.</span>sync (filename)](#apidoc.element.md5-file.promise.sync)



# <a name="apidoc.module.md5-file"></a>[module md5-file](#apidoc.module.md5-file)

#### <a name="apidoc.element.md5-file.promise"></a>[function <span class="apidocSignatureSpan">md5-file.</span>promise (filename)](#apidoc.element.md5-file.promise)
- description and source-code
```javascript
function md5FileAsPromised(filename) {
  return new Promise(function (resolve, reject) {
    md5File(filename, function (err, hash) {
      if (err) return reject(err)

      resolve(hash)
    })
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.md5-file.sync"></a>[function <span class="apidocSignatureSpan">md5-file.</span>sync (filename)](#apidoc.element.md5-file.sync)
- description and source-code
```javascript
function md5FileSync(filename) {
  var fd = fs.openSync(filename, 'r')
  var hash = crypto.createHash('md5')
  var buffer = new Buffer(BUFFER_SIZE)

  try {
    var bytesRead

    do {
      bytesRead = fs.readSync(fd, buffer, 0, BUFFER_SIZE)
      hash.update(buffer.slice(0, bytesRead))
    } while (bytesRead === BUFFER_SIZE)
  } finally {
    fs.closeSync(fd)
  }

  return hash.digest('hex')
}
```
- example usage
```shell
...
md5File('LICENSE.md', (err, hash) => {
  if (err) throw err

  console.log('The MD5 sum of LICENSE.md is: ${hash}')
})

/* Sync usage */
const hash = md5File.sync('LICENSE.md')
console.log('The MD5 sum of LICENSE.md is: ${hash}')
'''

## Promise support

If you require 'md5-file/promise' you'll receive an alternative API where all
functions that takes callbacks are replaced by 'Promise'-returning functions.
...
```



# <a name="apidoc.module.md5-file.promise"></a>[module md5-file.promise](#apidoc.module.md5-file.promise)

#### <a name="apidoc.element.md5-file.promise.promise"></a>[function <span class="apidocSignatureSpan">md5-file.</span>promise (filename)](#apidoc.element.md5-file.promise.promise)
- description and source-code
```javascript
function md5FileAsPromised(filename) {
  return new Promise(function (resolve, reject) {
    md5File(filename, function (err, hash) {
      if (err) return reject(err)

      resolve(hash)
    })
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.md5-file.promise.sync"></a>[function <span class="apidocSignatureSpan">md5-file.promise.</span>sync (filename)](#apidoc.element.md5-file.promise.sync)
- description and source-code
```javascript
function md5FileSync(filename) {
  var fd = fs.openSync(filename, 'r')
  var hash = crypto.createHash('md5')
  var buffer = new Buffer(BUFFER_SIZE)

  try {
    var bytesRead

    do {
      bytesRead = fs.readSync(fd, buffer, 0, BUFFER_SIZE)
      hash.update(buffer.slice(0, bytesRead))
    } while (bytesRead === BUFFER_SIZE)
  } finally {
    fs.closeSync(fd)
  }

  return hash.digest('hex')
}
```
- example usage
```shell
...
md5File('LICENSE.md', (err, hash) => {
  if (err) throw err

  console.log('The MD5 sum of LICENSE.md is: ${hash}')
})

/* Sync usage */
const hash = md5File.sync('LICENSE.md')
console.log('The MD5 sum of LICENSE.md is: ${hash}')
'''

## Promise support

If you require 'md5-file/promise' you'll receive an alternative API where all
functions that takes callbacks are replaced by 'Promise'-returning functions.
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
