# Best Foot Forward

^^

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

^^

# Loading

## WebAudio

```javascript
var audioBuffer;
if(audioContext){
  var request = new XMLHttpRequest();
  request.open('GET', 'epic-theme.mp3', true);
  request.responseType = 'arraybuffer';

  function decodeAudioData(e){
    audioContext.decodeAudioData(e.target.response, function(buffer){
      audioBuffer = buffer;
    }, onError);
  }

  request.addEventListener('load', decodeAudioData);
  request.send();
}
```

^^

# Loading

## HTML5 Audio

```javascript
audio.src = 'epic-theme.mp3';
```

^^

# Playing

## WebAudio

```javascript
var source = audioContext.createBufferSource();
source.buffer = audioBuffer;
source.connect(audioContext.destination);
source.start(0); // source.noteOn(0);
```

## HTML5

```javascript
audio.play();
```

^^

# Volume

## WebAudio

```javascript
var gainNode = audioContext.createGain();
source.connect(gainNode);
gainNode.connect(audioContext.destination);

gainNode.gain.value = 0.5;
```

## HTML5

```javascript
audio.volume = 0.5;
```

^^

# So Complicated

^^

# Still Better

^^
