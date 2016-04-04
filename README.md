# node-keyboard

:warning: requires sudo

Quick & dirty keyboard keylogger for NodeJS & Linux

Inspired from http://nodebits.org/linux-joystick

## Install

```
npm install git+https://github.com/ewnd9/node-keyboard.git
```

## Usage

```
$ sudo KEYBOARD_DRIVER=event2 node demo
```

See demo.js

```js
var Keyboard = require('./keyboard.js');

var k = new Keyboard('event2'); // 'event2' is the file corresponding to my keyboard in /dev/input/
k.on('keyup', console.log);
k.on('keydown', console.log);
k.on('keypress', console.log);
k.on('error', console.error);
```

## Events

```js
{
  timeS: 1347572085, // Timestamp ( Seconds part )
  timeMS: 741381, // Timestamp ( Microseconds part )
  keyCode: 17, // Keyboard code
  keyId: 'KEY_W', // Key ID /!\ Qwerty layout !
  type: 'keypress', // Event type
  dev: 'event2'  // Device
}
```

## Problems

- [ ] How to detect a keyboard layout?

## Licence

MIT
