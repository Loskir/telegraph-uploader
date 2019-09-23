# telegraph-uploader

A package that helps you to upload media files to [telegra.ph](https://telegra.ph).

## Usage

#### By buffer
```
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
```
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

#### HTTP Proxy


```
const {uploadByUrl} = require('telegraph-uploader')

uploadByUrl('https://link.to/image', 'http://user:pass@1.1.1.1:8888')
  .then((result) => {/*...*/})
```