# project_04
Parallax.js
Simple parallax scrolling effect inspired by Spotify.com implemented as a jQuery plugin
http://pixelcog.com/parallax.js/

Installation
Download and include parallax.min.js in your document after including jQuery.

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="/path/to/parallax.js"></script>
Usage
Via data attributes
To easily add a parallax effect behind an element, add data-parallax="scroll" to the element you want to use, and specify an image with data-image-src="/path/to/image.jpg".

<div class="parallax-window" data-parallax="scroll" data-image-src="/path/to/image.jpg"></div>
Via JavaScript
To call the parallax plugin manually, simply select your target element with jQuery and do the following:

$('.parallax-window').parallax({imageSrc: '/path/to/image.jpg'});
Notes
What parallax.js will do is create a fixed-position element for each parallax image at the start of the document's body. This mirror element will sit behind the other elements and match the position and dimensions of its target object.

Due to the nature of this implementation, you must ensure that these parallax objects and any layers below them are transparent so that you can see the parallax effect underneath. Also, if there is no other content in this element, you will need to ensure that it has some fixed dimensions otherwise you won't see anything.

.parallax-window {
	min-height: 400px;
	background: transparent;
}
Options
Options can be passed in via data attributes of JavaScript. For data attributes, append the option name to data-, as in data-image-src="".

Note that when specifying these options as html data-attributes, you should convert "camelCased" variable names into "dash-separated" lower-case names (e.g. zIndex would be data-z-index="").

Name	type	default	description
imageSrc	path	null	You must provide a path to the image you wish to apply to the parallax effect.
naturalWidth	number	auto	You can provide the natural width and natural height of an image to speed up loading and reduce error when determining the correct aspect ratio of the image.
naturalHeight	number	auto
position	xPos yPos	center center	This is analogous to the background-position css property. Specify coordinates as top, bottom, right, left, center, or pixel values (e.g. -10px 0px). The parallax image will be positioned as close to these values as possible while still covering the target element.
positionX	xPos	center
positionY	yPos	center
speed	float	0.2	The speed at which the parallax effect runs. 0.0 means the image will appear fixed in place, and 1.0 the image will flow at the same speed as the page content.
zIndex	number	-100	The z-index value of the fixed-position elements. By default these will be behind everything else on the page.
bleed	number	0	You can optionally set the parallax mirror element to extend a few pixels above and below the mirrored element. This can hide slow or stuttering scroll events in certain browsers.
iosFix	boolean	true	iOS devices are incompatable with this plugin. If true, this option will set the parallax image as a static, centered background image whenever it detects an iOS user agent. Disable this if you wish to implement your own graceful degradation.
androidFix	boolean	true	If true, this option will set the parallax image as a static, centered background image whenever it detects an Android user agent. Disable this if you wish to enable the parallax scrolling effect on Android devices.
Contributing
If you have a pull request you would like to submit, please ensure that you update the minified version of the library along with your code changes. This project uses uglifyjs to perform code compression.

Please use the following command:

uglifyjs parallax.js --comments -m -c -o parallax.min.js
LICENSE
The MIT License (MIT)

Copyright (c) 2015 PixelCog Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE
