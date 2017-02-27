# VueOccupy
A Vue directive for occupying content places before the data has been loaded.

# Install
Using `yarn` or `npm` to install `vue-occupy`:

```
# yarn
yarn add vue-occupy

#npm
npm install vue-occupy
```

# Usage
In your `main.js` file:

```
import VueOccupy from 'vue-occupy'

Vue.use(VueOccupy)
```

Now `vue-occupy` is a global Vue directive, you can use `v-occupy` in every `.vue` file.

# Params

| param | type | description | necessary |
| --- | --- | --- |
| data | {Object} | the data you bind to the node | Yes |
| config | {Object} | the color lump's css config | No |

For example:

```
<template>
  <div id="app" style="width:200px;height:50px;">
    <div v-occupy="{ data: content, config }"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      content: '',
      config: {
        width: '200px',
        height: '18px',
        background: '#ddd'
      }
    }
  },
  mounted () {
    fetch(url).then((result) => {
      this.content = result
    })
  }
}
</script>
```

Before the `fetch` method has requested the result data, the `div` with `v-occupy="{ data: content, config }"` would be occupying by a rectangle color lump. Once the data was loaded, the attribute `content` would be updated and be rendered into the html.

# Lisence
MIT