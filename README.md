# micro-upload

An [express-fileupload](https://npm.im/express-fileupload) wrapper for [micro](https://github.com/zeit/micro)

## Install

```
$ npm install --save micro-upload
```

## Usage

``` js
'use strict'

const { send } = require('micro')
const { upload, move } = require('micro-upload')

module.exports = upload(async (req, res) => {
  if (!req.files) {
    return send(res, 400, 'no file uploaded')
  }

  let file = req.files.file
  await move(file, `/tmp/uploads/${file.name}`)
  send(res, 200, 'upload success')
})
```
## Authors and Contributors

<table><tbody>
<tr><th align="left">Julián Duque</th><td><a href="https://github.com/julianduque">GitHub/julianduque</a></td><td><a href="http://twitter.com/julian_duque">Twitter/@julian_duque</a></td></tr>
</tbody></table>

Contributions are welcomed from anyone wanting to improve this project!

## License & Copyright

**micro-upload** is Copyright (c) 2017 Julian Duque and licensed under the MIT license. All rights not explicitly granted in the MIT license are reserved. See the included [LICENSE.md](https://github.com/julianduque/micro-upload/blob/master/LICENSE.md) file for more details.

