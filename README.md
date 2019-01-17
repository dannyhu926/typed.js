[![Build Status](https://travis-ci.org/mattboldt/typed.js.svg?branch=typed-2.0)](https://travis-ci.org/mattboldt/typed.js)
[![Code Climate](https://codeclimate.com/github/mattboldt/typed.js/badges/gpa.svg)](https://codeclimate.com/github/mattboldt/typed.js)
[![GitHub release](https://img.shields.io/github/release/mattboldt/typed.js.svg)]()
[![npm](https://img.shields.io/npm/dt/typed.js.svg)](https://img.shields.io/npm/dt/typed.js.svg)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/mattboldt/typed.js/master/LICENSE.txt)

<img src="https://raw.githubusercontent.com/mattboldt/typed.js/master/logo-cropped.png" width="450px" title="Typed.js" />

### [Live Demo](http://www.mattboldt.com/demos/typed-js/) | [View All Demos](http://www.mattboldt.com/typed.js) | [View Full Docs](http://www.mattboldt.com/typed.js/docs) | [mattboldt.com](http://www.mattboldt.com)

Typed.js is a library that types. Enter in any string, and watch it type at the speed you've set, backspace what it's typed, and begin a new sentence for however many strings you've set.

---

Installation
------------

#### Choose One

~~~
npm install typed.js
yarn add typed.js
bower install typed.js
~~~

#### CDN

~~~
<script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.9"></script>
~~~

#### Setup

This is really all you need to get going.

~~~ javascript
// Can also be included with a regular script tag
import Typed from 'typed.js';

var options = {
  strings: ["<i>First</i> sentence.", "&amp; a second sentence."],
  typeSpeed: 40
}

var typed = new Typed(".element", options);
~~~



### Strings from static HTML (SEO Friendly)
Rather than using the `strings` array to insert strings, you can place an HTML `div` on the page and read from it.
This allows bots and search engines, as well as users with JavaScript disabled, to see your text on the page.

~~~ javascript
<script>
  var typed = new Typed('#typed', {
    stringsElement: '#typed-strings'
  });
</script>
~~~

~~~ html
<div id="typed-strings">
    <p>Typed.js is a <strong>JavaScript</strong> library.</p>
    <p>It <em>types</em> out sentences.</p>
</div>
<span id="typed"></span>
~~~

### Type Pausing

You can pause in the middle of a string for a given amount of time by including an escape character.

~~~ javascript
var typed = new Typed(".element", {
  // Waits 1000ms after typing "First"
  strings: ["First ^1000 sentence.", "Second sentence."]
});
~~~

### Smart Backspacing

In the following example, this would only backspace the words after "This is a"

~~~ javascript
var typed = new Typed(".element", {
  strings: ["This is a JavaScript library", "This is an ES6 module"],
  smartBackspace: true // Default value
});
~~~

### Bulk Typing

The following example would emulate how a terminal acts when typing a command and seeing its result. 

~~~ javascript
var typed = new Typed(".element", {
  strings: [
    "git push --force ^1000\n `pushed to origin with option force`"
  ]
});
~~~

### CSS

CSS animations are built upon initialzation in JavaScript. But, you can customize them at your will! These classes are:
```css
/* Cursor */
.typed-cursor {}

/* If fade out option is set */
.typed-fade-out {}
```

### Use with ReactJS

Check out this example React app using Typed.js in a component: https://jsfiddle.net/mattboldt/ovat9jmp/

### Use with Vue.js

Check out the Vue.js component: https://github.com/Orlandster1998/vue-typed-js

Customization
----

~~~ javascript
var typed = new Typed(".element", {
  /**
   * @property {array} strings strings to be typed
   * @property {string} stringsElement ID of element containing string children
   */
  strings: ['These are the default values...', 'You know what you should do?', 'Use your own!', 'Have a great day!'],
  onStringTyped: function(index, self) { console.log(self.el.innerHTML); }
});

function next(typed) {
  typed.strings =['aaa','bbb']; //ajax get data
  typed.reset();
}
~~~
html标签支持打字暂停，点击后继续打字
<img typejs="pause" onclick="typing.resume()" src="/upload/image/20181119/20181119163818_91823.png" />

var typing = new Typing({
source: document.getElementById('type_source'),
output: document.getElementById('type_output'),
delay: 120,
scrollTop: function () {
    $$(".page-content").scrollTop($$(".page-content").height() + 99999);
},
done: function() {
    $("#answerForm").fadeIn(3000);
} //完成打印后的回调事件
});
typing.start();

$$('.page-content').on('touchmove', function (event) {
	typing.pause();
});

$$('.page-content').on('click', function (event) {
	typing.resume();
});

