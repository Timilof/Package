# Package
## Installation
[npm][]:
```bash
npm install package
```
## Usage
```javascript
'use strict';
var repeat = require('repeat-string');
/* Expose `vowel` as default function: vowel = require('this package'). */
module.exports = vowel;
/* Add other functions on `vowel`: inner = require('this package').inner. */
vowel.vowel = vowel;
vowel.inner = inner;
vowel.grawlix = grawlix;
var floor = Math.floor;
var defaultCharacter = '*';
var grawlixPattern = '@#$%!&?';
var vowels = /[aeiouy]/g;
/* `butt` > `b*tt` */
function vowel(value, character) {
  return value.replace(vowels, character || defaultCharacter);
}
/* `butt` > `b**t` */
function inner(value, character) {
  if (value.length <= 2) {
    return value;
  }
  return value.charAt(0) +
    repeat(character || defaultCharacter, value.length - 2) +
    value.charAt(value.length - 1);
}
/* `butt` > `@#$%` */
function grawlix(value, pattern) {
  var chars = pattern || grawlixPattern;
  var length = typeof value === 'number' ? value : value.length;
  var count = chars.length;
  return repeat(chars, floor(length / count)) + chars.slice(0, length % count);
}
```
###### Returns
return repeat(chars, floor(length / count)) + chars.slice(0, length % count);
## License
MIT


Add CommentCollapse 
 Blok Tech is on a roll
Your team’s now 95 members strong, with 5092 messages sent across 6 channels. You can track your team’s progress via the main menu.
Show Me

