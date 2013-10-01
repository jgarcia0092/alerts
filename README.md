# alerts.js

Simple and **straigtforward** notifications for the browser.

Alerts stack up. You dismiss them with a click (and also get them dismissed by themselves after some time by setting the `timeout` option). 

## Install

```bash
npm install alerts
```

Or if you feel cooler.

```bash
bower install alerts
```

AMD supported.

If used in good old `<script>` tag, it attaches itself to the `window` object as `al`.

## API

### alert(message[, options])

- message `String`
- options `Object`
- Returns `Object` an Alert instance

#### options

- timeout `Number` Time in miliseconds after which the alert is dismissed
- className `String` Custom class name to be added to each alert element
- onshow `Function` To be called when alert gets shown, with the alert element as context plus the options object as first argument, so anything you pass in is there
- ondismiss `Function` To be called after alert gets dismissed, with Alert instance (not the object, remember the element is about to be removed from the DOM) as context and options object as first argument

## Usage

Pretty straightforward.

´´´js
var alert = require('alert');

alert('Foo');
´´´

Basic CSS you need to get it working.

´´´css
.alerts {
	position: fixed;
	z-index: 10000;
	width: 13.500em;
	top: 1em;
	right: 1em;
}

.alerts > div {
	padding: .8em;
	margin-bottom: .4em;
	background-color: rgba(200, 200, 200, 0.8);
	cursor: default;
}
´´´

Passing in some options.

´´´js
var alerted = alert('Some error', {
  timeout: 4000,
  className: 'alert-error'
});

// The HTML element is available at alerted.el
´´´

### Transitions

If you want to use CSS transitions to either fade alerts in and out or swap them from right to left and viceversa, you can. Just set the `alert.transitionTime` property to the transition duration in miliseconds.

´´´js
alert.transitionTime = 400;
´´´

### And more

You also have the `Alert` constructor plus the `container` element at your disposal.

´´´js
// The constructor
var alerted = new alert.Alert('Foo');

// The element
alert.container.style.backgroundColor = 'lime';
´´´

## Browser support

It should work everywhere. Need to write tests.

## TODO

- Tests
- Demo

## License

(MIT)

Copyright (c) 2013 Arturo Castillo Delgado <19@8302.net>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.