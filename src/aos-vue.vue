<script>
import AOS from "aos";
import "aos/dist/aos.css";
import { defineComponent } from "vue";

export default defineComponent({
  name: "AosVue",
  mounted() {
    AOS.init();
    AOS.refresh();
  },
  props: {
    animation: {
      type: String,
      required: true,
    },
    offset: {
      type: String,
      required: false,
      default: 0,
    },
    once: {
      type: Boolean,
      required: false,
      default: false,
    },
    mirror: {
      type: Boolean,
      required: false,
      default: true,
    },
    easing: {
      type: String,
      required: false,
      default: "ease-in-out",
    },
    duration: {
      type: Number,
      required: false,
      default: 400,
    },
    delay: {
      type: Number,
      required: false,
      default: 0,
    },
    anchor: {
      type: String,
      required: false,
      default: null,
    },
  },
});
</script>

<template>
  <div
    :data-aos="animation"
    :data-aos-duration="duration"
    :data-aos-easing="easeing"
    :data-aos-mirror="mirror"
    :data-aos-once="once"
    :data-aos-offset="offset"
    :data-aos-delay="delay"
    :data-aos-anchor="anchor"
  >
    <slot />
  </div>
</template>
