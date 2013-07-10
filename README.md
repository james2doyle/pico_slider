pico_slider
===========

Create sliders(image lists) inside the [Pico CMS](http://pico.dev7studios.com/). Uses Swipe.js slider.

### Use Cases

This plugin really just reads images and outputs them in an array to be used on the front end. You could use any slider library that you want really. I like Swipe because I just find it to be the best since there is no jQuery required and it works amazingly well on mobile devices.

### Installation

* Clone this repo into your plugins folder.
* Do not change the name. Leave it as `pico_slider`.
* Download [Swipe](https://github.com/bradbirdsall/Swipe).
* Setup Swipe in your theme.
* Create a folder inside `content` called `images`. Path would be `{pico_root}/content/images/`.
* Inside that folder, drop all the images you want to use. (structure can be changed, defaut is `.jpg` images)
* Add the markup into your theme or mardown file
* Have fun!

### Markup

This is specific to swipe. You can do whatever you like for your slider library.

```html
<div id="slider" class='swipe'>
  <div class="swipe-wrap">
    {% for image in images %}
      <div class="swipe-slide">
        <img src="{{ image.url }}" alt="{{ image.name }}" width="{{ image.width }}" height="{{ image.height }}">
      </div>
    {% endfor %}
  </div>
</div>
```

### Image properties

Here is what is stored in each image item.

```php
$image = array(
  'name' = 'mylittlepony', // basically just the file name without the extension
  'width' = 900,
  'height' = 600,
  'url' = 'content/image/mylittlepony.jpg' // basically just the base_url + the image url
);
```

### Customizing Paths and Extensions

By default the plugin will only grab `.jpg` images. This can be changed in the `pico_slider.php` file.

```php
private $image_path = 'content/images'; // the path to the folder you want to use for loading the images
private $image_ext = '.jpg'; // the extension of the files you are looking for
```

### License

(The MIT License)

Copyright (c) <2013> James Doyle([@james2doyle](http://twitter.com/james2doyle)) james2doyle@gmail.com

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.