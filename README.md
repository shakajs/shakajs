# shakajs

```bash
# not available yet :(
npm install shakajs
```

```html
<script setup>
  import { Shaka } from "shakajs"
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
    poster="https://storage.googleapis.com/shaka-asset-icons/sintel.webp"
    :ui='{
      "addSeekBar": false,
      "controlPanelElements": ["play_pause", "time_and_duration", "spacer", "overflow_menu"],
      "overflowMenuButtons": ["quality", "captions"]
    }'
  ></Shaka>
</template>
```

```vue
<style>
  :root {
    --shaka-object-fit: contain;
    --shaka-background-color: #000000;
    --shaka-aspect-ratio: 16 / 9;
    --shaka-width: 720px;
    --shaka-height: unset;
  }
</style>
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
