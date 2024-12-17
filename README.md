# shakajs

```bash
npm install @shakajs/shakajs
```

```html
<script setup>
  import { Shaka } from "@shakajs/shakajs"
</script>
```

```vue
<template>
  <Shaka src="https://storage.googleapis.com/shaka-demo-assets/sintel/dash.mpd"></Shaka>
</template>
```

```vue
<template>
  <Shaka
    src="https://storage.googleapis.com/shaka-demo-assets/sintel/dash.mpd"
    :ui='{
      "addSeekBar": false,
      "controlPanelElements": ["play_pause", "time_and_duration", "spacer", "overflow_menu"],
      "overflowMenuButtons" : ["quality", "captions"]
    }'
  ></Shaka>
</template>
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
