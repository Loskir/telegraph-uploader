# telegraph-uploader

A package that helps you to upload media files to [telegra.ph](https://telegra.ph).

## Usage

#### `uploadByBuffer`
`uploadByBuffer(buffer, contentType, [agent]) => Promise<Response>`

#### `uploadByUrl`
`uploadByUrl(url, [agent]) => Promise<Response>`

#### Agent
An instance of `https.Agent` class (you can use this for proxies, search [`https-proxy-agent`](https://npmjs.com/https-proxy-agent), [`socks5-proxy-agent`](https://npmjs.com/https-proxy-agent) etc.)

#### Response
`{link: String, path: String}`

## Examples

#### By buffer
```javascript
const {uploadByBuffer} = require('telegraph-uploader')
const fs = require('fs')

uploadByBuffer(fs.readFileSync('image.png'), 'image/png')
  .then((result) => {
    console.log(result)
    /* {
         link: 'https://telegra.ph/file/...',
         path: '/file/...',
       } */
  })
```

#### By URL
```javascript
const {uploadByUrl} = require('telegraph-uploader')

uploadByUrl('https://link.to/image')
  .then((result) => {
    console.log(result)
    /* {
         link: 'https://telegra.ph/file/...',
         path: '/file/...',
       } */
  })
```