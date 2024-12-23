# shakajs

```bash
npm install shakajs
```

```html
<script setup>
  import { Shaka } from "shakajs"
</script>
```

```vue
<template>
  <Shaka src="https://storage.googleapis.com/shaka-demo-assets/angel-one/dash.mpd"></Shaka>
</template>
```

```vue
<template>
  <Shaka
    src="https://storage.googleapis.com/shaka-demo-assets/angel-one-widevine/dash.mpd"
    poster="https://storage.googleapis.com/shaka-asset-icons/angel_one.webp"
    :autoplay="true"
    :muted="false"
    :loop="false"
    :streaming='{
      "lowLatencyMode": true,
      "inaccurateManifestTolerance": 0,
      "rebufferingGoal": 0.01,
    }'
    :drm='{
      "servers": { "com.widevine.alpha": "https://cwip-shaka-proxy.appspot.com/no_auth" }
    }'
    :ui='{
      "addSeekBar": false,
      "controlPanelElements": ["play_pause", "time_and_duration", "spacer", "overflow_menu"],
      "overflowMenuButtons": ["quality", "captions"]
    }'
  ></Shaka>
</template>
```

<!---```vue
<style>
  :root {
    --shaka-object-fit: contain;
    --shaka-background-color: #000000;
    --shaka-aspect-ratio: 16 / 9;
    --shaka-width: 720px;
    --shaka-height: unset;
  }
</style>
```--->