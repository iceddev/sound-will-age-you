# Best Foot Forward

<aside class="notes">
  First implementation of Sound in Frozen - WebAudio only, otherwise nothing
</aside>

--

## Something Right

<ul class="fragment">
  <li>Started with WebAudio</li>
</ul>

<h2 class="fragment">Something Horribly Wrong</h2>

<ul class="fragment">
  <li>Only WebAudio</li>
</ul>

<aside class="notes">
  And hope browser support increases
</aside>

--

## Browser Support?

![WebAudio Support](img/webaudio_support.png)

[Firefox Bug](https://bugzilla.mozilla.org/show_bug.cgi?id=779297) | [Android Bug](https://code.google.com/p/chromium/issues/detail?id=112930)

<aside class="notes">
  Has been in Chrome since v10, just now getting to iOS and still not in Chrome for Android or Firefox
</aside>

--

# Start with WebAudio

## What Do We Get?

* High Performance
* Low Latency
* Uses Buffers instead of Resource Loading

--

# But Fall Back

## Browser support

--

# Initialization

## WebAudio

```javascript
var audioContext;
if(window.AudioContext){
  audioContext = new window.AudioContext();
}
```

## HTML5 Audio

```javascript
var audio = new Audio();
```

--

# Loading

## WebAudio

```javascript
var audioBuffer;
if(audioContext){
  var request = new XMLHttpRequest();
  request.open('GET', 'epic-theme.mp3', true);
  request.responseType = 'arraybuffer'; // Need to get an ArrayBuffer

  function decodeAudioData(e){
    // async decode
    audioContext.decodeAudioData(e.target.response, function(buffer){
      audioBuffer = buffer;
    }, onError);
  }

  request.addEventListener('load', decodeAudioData);
  request.send();
}
```

--

# Loading

## HTML5 Audio

```javascript
audio.src = 'epic-theme.mp3';
```

--

# Playing

## WebAudio

```javascript
// Place to attach our buffer
var source = audioContext.createBufferSource();
source.buffer = audioBuffer;
source.connect(audioContext.destination); // destination = output
source.start(0); // source.noteOn(0);
```

## HTML5

```javascript
audio.play();
```

--

# Volume

## WebAudio

```javascript
var gainNode = audioContext.createGain();
source.connect(gainNode);
// Connect gainNode to destination instead of source
gainNode.connect(audioContext.destination);

gainNode.gain.value = 0.5; // Change gain (volume)
```

## HTML5

```javascript
audio.volume = 0.5;
```

--

# So Complicated

--

# Extras!

* Mixing, Processing, Filtering
* Smooth Transitions
* Sound Creation
* Modular - Node System
* Designed for Future Features

--

# Turn This

![Synth](img/large_synth.jpg)

--

# Into This

![Browser Synth](img/browser_synth.png)
