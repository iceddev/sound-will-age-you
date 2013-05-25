# So...

## Much Better than Before

--

# Why We Need Sound

* Immersion
* Feedback
* Brand Recognition

--

# Start with Web Audio

* Scheduling
* Low Latency
* Filters
* Spatial Sounds

--

# Fallback to HTML5 Audio

* Basic streaming
* Can Layer Sounds
* Unfortunately, Not Low Latency
* Also, no effects

--

# Don't Fallback to Flash

* Does it give us anything more than Web Audio?
* Poor support (especially on mobile)
* Resource hog

--

# Push Web Audio Instead

[Android](https://code.google.com/p/chromium/issues/detail?id=112930)
|
[Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=779297)

_Enable in chrome://flags in Chrome Beta for Android_

--

# Still Need to Improve

* Mobile: [Android](https://code.google.com/p/chromium/issues/detail?id=178297) | [iOS](http://developer.apple.com/library/safari/#documentation/AudioVideo/Conceptual/Using_HTML5_Audio_Video/Device-SpecificConsiderations/Device-SpecificConsiderations.html)
* `canPlayType` & string comparison?
* Better abstractions & fallbacks

--

# Web Audio Abstractions

* [Howler.js](https://github.com/goldfire/howler.js)
* [WebAudio.js](http://jeromeetienne.github.io/webaudio.js/)
* [WAAPISim](http://www.g200kg.com/docs/waapisim/)
* [Audiolet](https://github.com/oampo/Audiolet)
* [audiolib.js](http://audiolibjs.org/)

--

# Game Sounds w/ Fallbacks

* [Frozen](http://frozenjs.com)
* [SoundJS](https://github.com/CreateJS/SoundJS)
* [Quintus](https://github.com/cykod/Quintus/blob/master/lib/quintus_audio.js)
* [Audia](https://github.com/mandarinx/audia)
