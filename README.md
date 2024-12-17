# shakajs

```bash
npm install @shakajs/shakajs
```

```js
import { Shaka } from '@shakajs/shakajs'
```

```html
<Shaka
  src="<manifest-url>"
  :live="false"
  :autoplay="true"
  :loop="false"
  :muted="true"
></Shaka>
```

```html
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
```
