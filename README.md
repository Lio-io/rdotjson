# rdotjson

Android String Resource XML Parser

## SYNOPSIS

```js
var fs = require("fs");
var rdotjson = require("rdotjson");

var xml = fs.readFileSync("strings.xml");

rdotjson(xml, function (err, R) {
  if (err) throw err;
  console.log(R.string.welcome);
});
```

## CLI

```sh
rdotjson app/src/main/res/values/strings.xml > strings.json

rdotjson app/src/main/res/values/*.xml > r.json

rdotjson app/src/production/res/values/*.xml > r_production.json

rdotjson app/src/develop/res/values/*.xml > r_develop.json

rdotjson app/src/main/res/values/strings.xml --format=csv > strings.csv
```

### CLI OPTIONS

`--exclude='*_android'` - Key name to exclude. Wildcard available.

`--format=json` - Output format. default: json

`--output=R.json` - Output filename. default: STDOUT

`--space=2` - JSON indent. default: 2

`-` - Input XML from STDIN

### CLI OUTPUT FORMATS

`--format=json --output=R.json` - JSON

`--format=csv --output=R.csv` - CSV

`--format=rdotswift --output=R.swift` - SWIFT ([rdotswift](https://github.com/kawanet/rdotswift) module required)

### JSON USAGE

```js
var R = require("./r.json");

console.warn(R.string.error_message);
```

## INSTALL

```sh
npm install -g kawanet/rdotjson
```

## REPOSITORY

- [https://github.com/kawanet/rdotjson](https://github.com/kawanet/rdotjson)

## LICENSE

The MIT License (MIT)

Copyright (c) 2016 Yusuke Kawasaki

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
