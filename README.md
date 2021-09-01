# **Vue Hamburgers**

[![](https://img.shields.io/npm/v/vue-hamburgers.svg?style=flat-square&color=cb3837&logo=npm&logoColor=ffffff)](https://www.npmjs.com/package/vue-hamburgers)
[![](https://img.shields.io/github/license/ewilan-riviere/vuepress-theme-useweb.svg?style=flat-square&color=f05032&logo=git&logoColor=ffffff)](https://github.com/ewilan-riviere/vue-hamburgers/blob/master/LICENSE)

[![node.js](https://img.shields.io/static/v1?label=Node.js&message=v12.16&color=339933&style=flat-square&logo=node.js&logoColor=ffffff)](https://nodejs.org/en/)
[![vue.js](https://img.shields.io/static/v1?label=Vue.js&message=v2.6&color=4FC08D&style=flat-square&logo=vue.js&logoColor=ffffff)](https://vuejs.org/)

Display a burger for menu as component, fork from [github.com/jonsuh/hamburgers](https://github.com/jonsuh/hamburgers), you can choose hamburger animation with prop `type`. Check [jonsuh.com/hamburgers](https://jonsuh.com/hamburgers/) for examples.

## **Documentation**

Install it with Yarn or NPM

```bash
yarn add -vue-hamburgers
```

**OR**

```bash
npm i vue-hamburgers --save
```

Import it, ES6 way, in `main.js` / `app.js` file

```js
import hamburger from 'vue-hamburgers'

Vue.use(hamburger)
```

### **For Nuxt.js**

Create a plugin like `plugins/vue-hamburgers.js`

```js
import Vue from 'vue'
import hamburger from 'vue-hamburgers'

Vue.use(hamburger)
```

In `nuxt.config.js` import plugin

```js
export default {
  // ...
  plugins: [{ src: '@/plugins/vue-hamburgers', mode: 'client' }]
  // ...
}
```

In any .vue component import in with `<client-only>`

```vue
<template>
  <client-only>
    <hamburger />
  </client-only>
</template>
```

### _Usage_

Use it in a `.vue` file

```vue
<template>
  <div>
    <hamburger />
  </div>
</template>
```

Define type with prop `type`

```html
<div>
  <hamburger type="3dx" />
</div>
```

### _API_

```vue
<template>
  <hamburger type="spring" :width="30" :height="3" :spacing="0.8" color="red" />
</template>
```

Check all available type on [jonsuh.com/hamburgers](https://jonsuh.com/hamburgers/), use it in lowercase like this `type="arrow"`

Set the active state using the `active` prop. This is useful when you need to access the state of the hamburger in the parent. It can be done like this:

```vue
<template>
  <div>
    <hamburger
      type="spring"
      :width="30"
      :height="3"
      :spacing="1"
      color="green"
      :active="isActive"
      @toggle="toggle"
    />
    <h1 v-if="isActive">This will show when you click the hamburger!</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false
    }
  },
  methods: {
    toggle() {
      this.isActive = !this.isActive
    }
  }
}
</script>
```

Remember that you **must** have an `@toggle` function to modify the data of the parent, otherwise the toggle will still work, but it will have no effect on the parent data itself.

| Props   | Type            | Default  | Describe                                                                           |
| ------- | --------------- | -------- | ---------------------------------------------------------------------------------- |
| type    | String          | 'spring' | Type of hamburger animation                                                        |
| width   | Number / String | 40       | Define width of hamburger                                                          |
| height  | Number / String | 4        | Define height of bars of hamburger                                                 |
| spacing | Number / String | 1        | Define spacing between bars of hamburger, reduce with '0.8' or increase with '1.2' |
| color   | String          | #000000  | Set color with hexa code                                                           |
| active  | Boolean         | false    | Set active state                                                                   |
| @toggle | Function        | none     | Callback function when the button is clicked                                       |

## **License**

**MIT** &copy; [**@jonsuh**](https://github.com/jonsuh), [**@ewilan-riviere**](https://github.com/ewilan-riviere)
