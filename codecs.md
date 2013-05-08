## Codecs

![Codec Support](img/codecs.png)

^^

# canPlayType

```javascript
var audio = new Audio();
audio.canPlayType('audio/webm');
// "maybe"

audio.canPlayType('audio/webm; codecs="vorbis"');
// "probably"

audio.canPlayType('audio/obscure-type');
// ""
```
* Chrome on OSX

^^

# Full Browser Support

* MP3
  * Chrome
  * IE
  * Safari
  * Some FF
* WebM (or Ogg)
  * Chromium
  * FF
  * Opera
  * Chrome, Safari also support these

^^

# Which File?

```javascript
var audio = new Audio();

var sounds = [
  { type: 'audio/mpeg', filename: 'epic-theme.mp3' },
  { type: 'audio/webm', filename: 'epic-theme.webm' }
];

sounds.some(function(sound){
  return audio.canPlayType(sound.type) && (audio.src = sound.filename);
});
// Chrome, IE, Safari, Some FF: audio.src === 'epic-theme.mp3'
// Chromium, FF, Opera: audio.src === 'epic-theme.webm'
```
[Fiddle](http://jsfiddle.net/phated/YbjL9/)

^^

# Don't Silence Me, Bro

```javascript
audio.addEventListener('error', function(){
  sounds = sounds.filter(function(sound){
    return !new RegExp(sound.filename).test(audio.src);
  });

  sounds.some(function(sound){
    return audio.canPlayType(sound.type)
      && (audio.src = sound.filename);
  });
});
```
[Fiddle](http://jsfiddle.net/phated/YbjL9/1)

^^

# Maybe Try Probably

```javascript
var probably = [], maybe = [];

sounds.forEach(function(sound){
  var canPlay = audio.canPlayType(sound.type);
  if(canPlay === 'probably') return probably.push(sound.filename);
  if(canPlay === 'maybe') return maybe.push(sound.filename);
});

var sources = probably.concat(maybe);

audio.addEventListener('error', setSrc);

function setSrc(){
  sources.length && (audio.src = sources.shift());
}

setSrc();
```
[Fiddle](http://jsfiddle.net/phated/YbjL9/2/)

^^

# Function-ize

```javascript
function load(filename){
  var audio = new Audio();
  var sounds = [
    { type: 'audio/mpeg', filename: filename + '.mp3' },
    { type: 'audio/webm', filename: filename + '.webm' }
  ];
  // All That Boilerplate
  return audio;
}

load('epic-theme').play();
load('sad-song').play();
```
[Fiddle](http://jsfiddle.net/phated/YbjL9/3/)

^^

## It's My Party And I'll AMD If I Want To

```javascript
define([
  'frozen/plugins/loadSound!epic-theme'
], function(theme){

  theme.play();

});
```
[Fiddle](http://jsfiddle.net/phated/PN7EM/)