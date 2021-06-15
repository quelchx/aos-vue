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
      type: Number,
      required: false,
      default: 0,
    },
    duration: {
      type: Number,
      required: false,
      default: 400,
    },
    easing: {
      type: String,
      required: false,
      default: "ease-in-out",
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
    placement: {
      type: String,
      required: false,
      default: "top-center",
    },
    once: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
});
</script>

<template>
  <div
    :data-aos="animation"
    :data-aos-duration="duration"
    :data-aos-easing="easing"
    :data-aos-once="once"
    :data-aos-offset="offset"
    :data-aos-delay="delay"
    :data-aos-anchor="anchor"
    :data-aos-anchor-placement="placement"
  >
    <slot />
  </div>
</template>
