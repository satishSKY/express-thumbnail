# Express Thumbnail

Express thumbnail is a [Express framework](http://expressjs.com/) middleware for creation of thumbnails on the fly. 
It automatically creates a thumbnails by adding query parameters onto a image url.

## Examples

```js
var express = require('express');
var app = express();
var expressThumbnail = require(path to this middleware);
...
app.use(expressThumbnail.register(path to images directory));
```

```html
<img src="foo.png?thumb=50x50">
```

## Docs.

### expressThumbnail.register(rootDir, [options])

`rootDir` path to images root directory.

`options` (optional) an object of options. Available options:

* `cacheDir` The location where converted images will be stored. Default is `[rootDir]/.thumb`.
* `quality` Compression level. Default is 80. [more](http://aheckmann.github.io/gm/docs.html#quality). 
* `gravity` The direction the primitive gravitates to when annotating the image. Default is `Center`. [more](http://aheckmann.github.io/gm/docs.html#gravity).

## Dependencies

##### [ImageMagick](http://www.imagemagick.org)

Install on Ubuntu

    apt-get install imagemagick
    
* [gm](http://aheckmann.github.io/gm)
* [mkdirp](https://github.com/substack/node-mkdirp)