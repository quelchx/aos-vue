# AOS Vue

Vue 3 lightweight animate on scroll component.

### Notes:

This package utilizes a library called aos.js, which you can find [here](https://www.npmjs.com/package/aos). The design of This component is to leverage the aos.js library and its features -- but more customized towards the Vue way.

This package was built using [Rollup](https://www.npmjs.com/package/vue-sfc-rollup). Other than using what comes default with this package -- they're no other dependencies this project relies on (other than aos.js).

### Prerequisites

- Vue v.3.x
  - Package has been tested with Vue 3 only, but should work without any issues if using older versions of Vue.
  - If any issues persist please visit [issues](https://github.com/quelchx/aos-vue/issues) to report an issue -- and I will review it asap.

## Installation

```sh
npm install aos-vue
```

### CDN

```html
<script
  src="https://cdn.jsdelivr.net/npm/aos-vue@0.0.2/dist/aos-vue.esm.js"
  integrity="sha256-yEdgzK8/sKALhYXt7Wx989np5BDj6laj+r4bnEhx6Hw="
  crossorigin="anonymous"
></script>
```

---

## Usage

### Global

Registering the component globally, simple usage demonstration.

**main.js**

```js
import { createApp } from "vue";
import App from "./App.vue";
import AosVue from "aos-vue";
createApp(App).use(AosVue).mount("#app");
```

**App.vue**

```html
<template>
  <aos-vue animation="fade-in">
    <h2>{{message}}</h2>
  </aos-vue>
</template>

<script>
  export default {
    data() {
      return { message: "Animate" };
    },
  };
</script>
```

---

### Local

Simple usage

Registering the package locally, simple usage demonstration.

**App.vue**

```html
<template>
  <aos-vue animation="slide-up">
    <p>Hello World</p>
  </aos-vue>
</template>

<script>
  import AosVue from "aos-vue";
  export default {
    components: { AosVue },
  };
</script>
```

---

## Properties

#### Animation

The property will determine which animation is to occur depending on what parameter is passed.

- type: String
- required: true
- usage:

```html
<aos-vue animation="fade-in">Hello World</aos-vue>
```

> Animation Options

##### Fade Animations

- fade
- fade-up
- fade-down
- fade-left
- fade-right
- fade-up-right
- fade-up-left
- fade-down-right
- fade-down-left

##### Flip Animations

- flip-up
- flip-down
- flip-right
- flip-left

##### Slide Animations

- slide-down
- slide-up
- slide-right
- slide-left

##### Zoom Animations

- zoom-in
- zoom-in-up
- zoom-in-down
- zoom-in-left
- zoom-in-right
- zoom-out
- zoom-out-up
- zoom-out-down
- zoom-out-left
- zoom-out-right

---

#### Offsets

Change offset to trigger animations sooner or later

- type: Number
- required: false
- default: 0
- usage:

```html
<aos-vue animation="fade-in" :offset="200">Hello World</aos-vue>
```

**Note: amounts are pixel (px) amounts**

---

#### Durations

Duration of the animation play time (ms)

- type: Number
- required: false
- default: 400
- usage:

```html
<aos-vue animation="fade-in" :duration="600">Hello World</aos-vue>
```

**Note: `duration` accepts values from 50 to 3000, with step 50ms -- this should be good for all use cases. If this is an issue with the set range, you can change the CSS animation to the element you wish to target like the example shown below**

> (Example overriding default animation time)

```CSS
body [data-aos-duration='4000'] [data-aos],
[data-aos][data-aos][data-aos-duration='4000'] {
  transition-duration: 4000ms;
}
```

---

#### Easing

Change and choose timing function to ease elements in different ways

- type: String
- required: false
- default: 'ease-in-out'
- usage:

```html
<aos-vue animation="fade-in" easing="ease"></aos-vue>
```

##### Easing Options

- linear
- ease
- ease-in
- ease-out
- ease-in-out
- ease-in-back
- ease-out-back
- ease-in-out-back
- ease-in-sine
- ease-out-sine
- ease-in-out-sine
- ease-in-quad
- ease-out-quad
- ease-in-out-quad
- ease-in-cubic
- ease-out-cubic
- ease-in-out-cubic
- ease-in-quart
- ease-out-quart
- ease-in-out-quart

---

#### Delay

Delays the animation by milliseconds (ms).

- type: Number
- required: false
- default: 0
- usage:

```html
<aos-vue animation="fade-in" :delay="300">Hello World</aos-vue>
```

---

#### Anchors

Anchor element, whose offset will be counted to trigger animation instead of actual elements offset

- type: String
- required: false
- default: null
- usage

```html
<aos-vue animation="fade-in" anchor="#selector">Hello World</aos-vue>
```

---

#### Placement

Anchor placement - which one position of the element on the screen should trigger the animation

- type: String
- required: false
- default: 'top-center'
- usage:

```html
<aos-vue animation="fade-in" placement="top-bottom">Hello World</aos-vue>
```

#### Placement Options

- top-bottom
- top-center
- top-top
- center-bottom
- center-center
- center-top
- bottom-bottom
- bottom-center
- bottom-top

---

#### Once

Choose whether the animation should fire once, or every time you scroll up/down to the element

- type: Boolean
- required: false
- default: false
- usage:

```html
<aos-vue animation="fade-in" :once="true">Hello World</aos-vue>
```

### Issues

If you encounter any issues or have any concerns please refer to [issues](https://github.com/quelchx/aos-vue/issues) and report a detailed description of what is occurring.
