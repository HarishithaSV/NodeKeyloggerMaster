markdown

# Node.js Keylogger

A simple Node.js keylogger for Linux using event emitters.

## Overview

This Node.js keylogger captures every keystroke made by the user on their keyboard devices. It uses event emitters to listen to keyboard events and captures the timestamp, keycode, key ID, event type, and device information.

## Installation

To install the keylogger, use npm:

```sh
npm install node-keylogger

Usage

javascript

const Keyboard = require('node-keylogger');

// Initialize with your keyboard device (e.g., 'event0')
const k = new Keyboard('event0');

// Event listeners for different types of key events
k.on('keyup', console.log);
k.on('keydown', console.log);
k.on('keypress', console.log);

// Error handling
k.on('error', console.error);

Events

The keylogger emits the following events:

    keyup: Triggered when a key is released.
    keydown: Triggered when a key is pressed down.
    keypress: Triggered when a key is pressed and released.
    error: Triggered when an error occurs.

Each event object contains:

    timeS: Timestamp in seconds.
    timeMS: Timestamp in milliseconds.
    keyCode: Numeric key code.
    keyId: Key identifier (based on Qwerty layout).
    type: Event type (keyup, keydown, keypress).
    dev: Device name.

Example

javascript

{
  timeS: 1347572085,
  timeMS: 741381,
  keyCode: 17,
  keyId: 'KEY_W',
  type: 'keypress',
  dev: 'event2'
}

Development
TODO

    Add support for Windows.
    Add support for OSX.

License

This project is licensed under the ISC License. See the LICENSE file for details.
