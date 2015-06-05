Showdown's Youtube Extension
==========================

[![Build Status](https://travis-ci.org/showdownjs/youtube-extension.svg)](https://travis-ci.org/showdownjs/youtube-extension) [![npm version](https://badge.fury.io/js/showdown-youtube.svg)](http://badge.fury.io/js/showdown-youtube) [![npm version](https://badge.fury.io/bo/showdown-youtube.svg)](http://badge.fury.io/bo/showdown-youtube)

------

**An extension to embed [Youtube](http://youtube.com/) videos in showdown documents using markdown syntax**

## Introduction

This extension enables embedding youtube videos using markdown's image syntax. Instead of creating a new definition,
it borrows image syntax `![foo][bar.jpg]` to create an inframe pointing to the desired video.
Although it uses the same syntax as images, only valid youtube video links are actually parsed.
Basically it looks for urls that start with:
 - `http://www.youtube.com/watch?v=` or `youtube.com/watch?v=`
 - `http://www.youtube.com/embed/` or `youtube.com/embed/`
 - `http://youtu.be/` or `youtu.be/`

## Installation

### With [npm](http://npmjs.org)

    npm install showdown-youtube

### With [bower](http://bower.io/)

    bower install showdown-youtube

### Manual

You can also [download the latest release zip or tarball](https://github.com/showdownjs/youtube-extension/releases) and include it in your webpage, after showdown:

    <script src="showdown.min.js">
    <script src="showdown-youtube.min.js">

## Enabling the extension

After including the extension in your application, you just need to enable it in showdown.

    var converter = new showdown.Converter({extensions: ['youtube']});

## Example

```javascript
var converter = new showdown.Converter({extensions: ['youtube']}),
    input = '![youtube video](http://www.youtube.com/watch?v=dQw4w9WgXcQ)';
    html = converter.makeHtml(input);
console.log(html);
```

This should output the equivalent to:

```html
<iframe src="//www.youtube.com/embed/dQw4w9WgXcQ?rel=0" frameborder="0" allowfullscreen></iframe>
```

## License
These files are distributed under BSD license. For more information, 
please check the [LICENSE file](https://github.com/showdownjs/youtube-extension/blob/master/LICENSE) in the source code.
