# AOS Vue

Vue 3 lightweight animate on scroll component. Full website example coming soon.

For a quick small demonstation check out https://quelchlax.tech to see this package being used.

![npm](https://img.shields.io/npm/v/aos-vue?color=purple&style=flat-square)
[![](https://data.jsdelivr.com/v1/package/npm/aos-vue/badge)](https://www.jsdelivr.com/package/npm/aos-vue)
![npm](https://img.shields.io/npm/dt/aos-vue?color=green&style=flat-square)
![GitHub issues](https://img.shields.io/github/issues/quelchx/aos-vue?color=red&style=flat-square)
![GitHub last commit](https://img.shields.io/github/last-commit/quelchx/aos-vue?color=cyan&style=flat-square)

## Table Of Contents

- [Notes](#notes)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [NPM](#npm)
  - [CDN](#cdn)
- [Usage](#usage)
  - [Global](#global)
  - [Local](#local)
- [Props](#properties)
  - [Animation](#animation)
  - [Animation Options](#animations-options)
  - [Fade](#fade-animations)
  - [Flip](#flip-animations)
  - [Slide](#slide-animations)
  - [Zoom](#zoom-animations)
  - [Offset](#offset)
  - [Duration](#duration)
  - [Easing](#easing)
  - [Easing Options](#easing-options)
  - [Anchor](#anchor)
  - [Placement](#placement)
  - [Placement Options](#placement-options)
  - [Once](#once)

---

### Notes:

This package utilizes a library called aos.js, which you can find at https://www.npmjs.com/package/aos. The design of This component is to leverage the aos.js library and its features -- but more customized towards the Vue way.

This package was built using <a href='https://www.npmjs.com/package/vue-sfc-rollup'>vue-sfc-rollup</a>. Other than using what comes default with this package -- they're no other dependancies this project relies on (other than aos.js).

### Prerequisites

- Vue v.3.x
  - Package has been testing with Vue 3 only, but should work without any issues if using older versions of Vue.
  - If any issues persist please visit https://github.com/quelchx/aos-vue/issues to report an issue -- and I will review it asap.

## Installation

**NPM**
(Recommended)

```sh
npm install aos-vue
```

**CDN**

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

createApp(App)
  .use(AosVue)
  .mount("#app");
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

#### `animation`

Property will determine which animation is to occur depending on what parameter is passed.

- type: String
- required: true
- usage:

  ```html
  <aos-vue animation="fade-in">Hello World</aos-vue>
  ```

- #### `animations options`:

  #### **fade animations:**

  - fade
  - fade-up
  - fade-down
  - fade-left
  - fade-right
  - fade-up-right
  - fade-up-left
  - fade-down-right
  - fade-down-left

  #### **flip animations:**

  - flip-up
  - flip-down
  - flip-right
  - flip-left

  #### **slide animations:**

  - slide-down
  - slide-up
  - slide-right
  - slide-left

  #### **zoom animations**

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

#### `offset`

Change offset to trigger animations sooner or later

- type: Number
- required: false
- default: 0
- usage:

```html
<aos-vue animation="fade-in" :offset="200">Hello World</aos-vue>
```

- note: amounts are pixel (px) amounts

---

#### `duration`

Duration of the animation play time (ms)

- type: Number
- required: false
- default: 400
- usage:

```html
<aos-vue animation="fade-in" :duration="600">Hello World</aos-vue>
```

- note: `duration` accepts values from 50 to 3000, with step 50ms -- this should be good for all use cases. If this is an issue with the set range, you can change the css animation the element you wish to target like the example shown below

> (Example overriding default animation time)

```css
body [data-aos-duration="4000"] [data-aos],
[data-aos][data-aos][data-aos-duration="4000"] {
  transition-duration: 4000ms;
}
```

---

#### `easing`

Change and choose timing function to ease elements in different ways

- type: String
- required: false
- default: 'ease-in-out'
- usage:

```html
<aos-vue animation="fade-in" easing="ease"></aos-vue>
```

#### - **`easing options`**

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

#### `delay`

Delays the animation by milliseconds (ms).

- type: Number
- required: false
- default: 0
- usage:

```html
<aos-vue animation="fade-in" :delay="300">Hello World</aos-vue>
```

---

#### `anchor`

Anchor element, whose offset will be counted to trigger animation instead of actual elements offset

- type: String
- required: false
- default: null
- usage

```html
<aos-vue animation="fade-in" anchor="#selector">Hello World</aos-vue>
```

---

#### `placement`

Anchor placement - which one position of element on the screen should trigger animation

- type: String
- required: false
- default: 'top-center'
- usage:

```html
<aos-vue animation="fade-in" placement="top-bottom">Hello World</aos-vue>
```

#### - `placement options`

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

#### `once`

Choose wheter animation should fire once, or every time you scroll up/down to the element

- type: Boolean
- required: false
- default: false
- usage:

```html
<aos-vue animation="fade-in" :once="true">Hello World</aos-vue>
```

---

### Contribution

If your interested in contributing to this package please contact me by email through my website at https://quelchlax.tech

### Issues

If you encounter any issues or have any concerns please refer to https://github.com/quelchx/oas-vue/issues and report a detailed description of what is occuring.

Package Repository: https://github.com/quelchx/aos-vue

Author: Eric Quelch Github: https://github.com/quelchx Website: https://quelchlax.tech
