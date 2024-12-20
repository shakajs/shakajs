<template>
  <div class="shaka" ref="ShakaContainer">
    <video
      id="video"
      ref="Shaka"
      preload="auto"
      :autoplay="autoplay"
      :loop="loop"
      :muted="muted"
      :poster="poster"
    ></video>
  </div>
</template>

<script>
import * as shaka from "shaka-player/dist/shaka-player.ui.js";

export default {
  name: "Shaka",
  props: {
    src: {
      type: String,
      required: true,
    },
    poster: {
      type: String,
      required: false,
    },
    autoplay: {
      type: Boolean,
      default: false,
    },
    loop: {
      type: Boolean,
      default: false,
    },
    muted: {
      type: Boolean,
      default: false,
    },
    abr: {
      type: Object,
      default: () => ({}),
    },
    manifest: {
      type: Object,
      default: () => ({}),
    },
    drm: {
      type: Object,
      default: () => ({}),
    },
    streaming: {
      type: Object,
      default: () => ({}),
    },
    ui: {
      type: Object,
      default: () => ({}),
    },
  },
  data() {
    return {
      player: null,
    };
  },
  mounted() {
    shaka.polyfill.installAll();

    if (shaka.Player.isBrowserSupported()) {
      this.initPlayer();
    } else {
      console.error("Browser not supported!");
    }
  },
  unmounted() {
    if (this.player) {
      this.player.destroy();
    }
  },
  methods: {
    async initPlayer() {
      this.player = new shaka.Player();
      const ui = new shaka.ui.Overlay(
        this.player,
        this.$refs.ShakaContainer,
        this.$refs.Shaka
      );

      // Configure the player based on the stream type and provided configurations
      this.configurePlayer(this.player);
      this.configureUI(ui);

      try {
        // Attach the player to the media element
        await this.player.attach(this.$refs.Shaka);
        console.log("Player attached successfully!");

        // Load the video source
        await this.player.load(this.src);
        console.log("The video has now been loaded!");

      } catch (error) {
        this.onError(error);
      }
    },
    configurePlayer(player) {
      const config = {
        abr: this.abr,
        manifest: this.manifest,
        drm: this.drm,
        streaming: this.streaming,
      };

      player.configure(config);
    },
    configureUI(ui) {
      const config = {
        ...this.ui,
      };

      ui.configure(config);
    },
    onError(error) {
      console.error("Error code", error.code, "object", error);
    },
  },
};
</script>

<style>
@import '../../node_modules/shaka-player/dist/controls.css';

:root {
  --shaka-object-fit: contain;
  --shaka-background-color: #000000;
  --shaka-aspect-ratio: 16 / 9;
  --shaka-width: 720px;
  --shaka-height: unset;
}

.shaka {
  width: var(--shaka-width) !important;
  height: var(--shaka-height) !important;
  aspect-ratio: var(--shaka-aspect-ratio) !important; 
  display: inline-flex;
  overflow: hidden;
}

.shaka video {
  object-fit: var(--shaka-object-fit);
  height: 100%;
  width: 100%;
  background-color: var(--shaka-background-color);
}
</style>