<script>
import { defineComponent } from 'vue';
import AosVue from '@/aos-vue.vue';

export default defineComponent({
  name: 'ServeDev',
  components: {
    AosVue
  }
});
</script>

<template>
  <div id="app">
    <aos-vue animation='fade-in' :duration='2000'>
      <p>Hello World</p>
    </aos-vue>
  </div>
</template>
