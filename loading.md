# What's Expected?

## `audio.play()`

^^

# media.play()

Sets the paused attribute to false, <div class="fragment grow highlight-green">loading the media resource</div> and beginning playback if necessary. If the playback had ended, will restart it from the start.

[Spec](http://www.w3.org/html/wg/drafts/html/master/embedded-content-0.html#playing-the-media-resource)

^^

## Don't Need No Stinkin' Spec

<img class="fragment" src="img/chrome.png" alt="Chrome" />
<img class="fragment" src="img/firefox.png" alt="Firefox" />
<img class="fragment" src="img/ie.png" alt="Internet Explorer" />
<img class="fragment" src="img/opera.png" alt="Opera" />
<img class="fragment" src="img/safari.png" alt="Safari" />
<br />
<img class="fragment" src="img/no-ios.png" alt="iOS" />
<img class="fragment" src="img/no-android.png" alt="Android" />
<img class="fragment" src="img/androidfirefox.png" alt="Firefox for Android" />
<img class="fragment" src="img/firefoxos.png" alt="FirefoxOS" />

^^

# Excuses, Excuses

"In Safari on iOS (for all devices, including iPad), where the user may be on a cellular network and be charged per data unit, <span class="fragment highlight-green">preload and autoplay are disabled.</span>
No data is loaded until the user initiates it. This means the <span class="fragment highlight-green">JavaScript play() and load() methods are also inactive until the user initiates playback,</span>
unless the play() or load() method is triggered by user action. In other words, a user-initiated Play button works, but an onLoad="play()" event does not."

[Source](http://developer.apple.com/library/safari/#documentation/AudioVideo/Conceptual/Using_HTML5_Audio_Video/Device-SpecificConsiderations/Device-SpecificConsiderations.html)

^^

# On the Bandwagon

"This is intended. Autoplay is not honored on android as it will cost data usage."

[Source](https://code.google.com/p/chromium/issues/detail?id=138132#c6)

^^

# Meanwhile

We can download terabytes of images without any restrictions

^^

# Workaround

```javascript
var audio = new Audio();

audio.src = 'epic-theme.mp3';

function preloadSound(){
  audio.load();
  document.removeEventListener('touchstart', preloadSound);
}

document.addEventListener('touchstart', preloadSound);
```
[Fiddle](http://jsfiddle.net/phated/zAuXL/)

^^

# Now Do This

<h3 class="fragment">For Every Sound</h3>
<h3 class="fragment">Every Parallel Audio Stream</h3>
<h2 class="fragment">On Init of Your Game/App</h2>
<h1 class="fragment">On Mobile</h1>

^^

![NOOOOOPE](img/lana.png)