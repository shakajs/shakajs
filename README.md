# shakajs

```bash
npm install @shakajs/shakajs
```

```js
import { Shaka } from '@shakajs/shakajs'
```

```html
<Shaka 
  src="https://storage.googleapis.com/shaka-demo-assets/angel-one/dash.mpd"
  poster="shakajs.png"
  :autoplay="true"
  :muted="false"
  :loop="false"
></Shaka>
```

<!--```html
<Shaka src="<manifest-url>">
  <track src="en.vtt" kind="captions" label="en" srclang="en">
</Shaka>
```

```html
<Shaka>
  <source src="<manifest-url>">
</Shaka>
```

```html
<Shaka
  src="<manifest-url>"
  poster="shakajs.png"
></Shaka>
```-->

```html
<Shaka
  src="<manifest-url>"
  :controls=["play_pause", "time_and_duration", "fullscreen"]
  :menu=["picture_in_picture", "playback_rate"]
></Shaka>
```
