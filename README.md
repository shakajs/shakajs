# shakajs

```bash
npm install @shakajs/shakajs
```

```js
import { Shaka } from '@shakajs/shakajs'
```

```html
<Shaka src="https://storage.googleapis.com/shaka-demo-assets/angel-one/dash.mpd"></Shaka>
```

```html
<Shaka
  src="https://storage.googleapis.com/shaka-demo-assets/angel-one/dash.mpd"
  :ui='{
    "addSeekBar": false,
    "controlPanelElements": ["play_pause", "time_and_duration", "spacer", "fullscreen"]
  }'
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
