# So...

## Much Better than Before

^^

# Why We Need Sound

* Immersion
* Feedback
* Brand Recognition

^^

# Start with Web Audio

* Scheduling
* Low Latency
* Filters
* Spatial Sounds

^^

# Fallback to HTML5 Audio

* Basic streaming
* Can Layer Sounds
* Unfortunately, Not Low Latency
* Also, no effects

^^

# Don't Fallback to Flash

* Does it give us anything more than HTML5 Audio?
* Poor support (especially on mobile)
* Resource hog

^^

# Push Web Audio Instead

[Android](https://code.google.com/p/chromium/issues/detail?id=112930)
|
[Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=779297)

^^

# Still Need to Improve

* Mobile: [Android](https://code.google.com/p/chromium/issues/detail?id=178297) | [iOS](http://developer.apple.com/library/safari/#documentation/AudioVideo/Conceptual/Using_HTML5_Audio_Video/Device-SpecificConsiderations/Device-SpecificConsiderations.html)
* `canPlayType` & string comparison?
* Better abstractions

^^

# Notable Abstractions

* [Frozen](http://frozenjs.com)
* [SoundJS by CreateJS](https://github.com/CreateJS/SoundJS)
* [Quintus](https://github.com/cykod/Quintus/blob/master/lib/quintus_audio.js)