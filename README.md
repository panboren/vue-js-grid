## Vue.js Grid

#### Fixed size grid for Vue.js

This is very a first version of the plugin. If you find any bugs and/or want to contribute, feel free to create issues, PRs or reach me out on twitter! 👍 🚀

Thanks!

### Install
```
npm install --save vue-js-grid
```

```js
import Vue from 'vue'
import Grid from 'vue-js-grid'

Vue.use(Grid)
```

### Usage

```js
data () {
  return {
    items: [
      'a',
      'b',
      'c'
    ]
}
```

```vue
<grid
  :draggable="true"
  :sortable="true"
  :items="items"
  :height="100"
  :width="100">
  <template slot="cell" scope="props">
    <div>{{props.item}}</div>
  </template>
</grid>
```

### Props

| Name       | Type     | Default   | Description       |
| ---        | ---      | ---       | ---               |
| items      | [Object] | []        | |
| cellWidth  | Number   | 80        | |
| cellHeight | Number   | 80        | |
| draggable  | Boolean  | false     | |
| dragDelay  | Number   | 0         | @TODO |
| sortable   | Boolean  | false     | |
| center     | Boolean  | false     | @TODO |

### Events

| Name    | Description |
| ---     | ---         |
| @change | |
| @remove | |
| @click  | |
| @sort   | |

### Cell template

Cell template is used to get access to list data, indexing and sorting params generated by plugin.

Template's scope contains:

`props.item` - list item value 

`props.index` - initial index of the item

`props.sort` - current index of an item after sorting

`props.remove()` - method that will remove item from the arrey and resport list.

Example:

```vue
<template slot="cell" scope="props">
  <div @click="() => { props.remove() }">
    <div>Data: {{props.item}}</div>
    <div>{{props.index}} / {{props.sort}}</div>
</template>
```

### Roadmap

1. Add element insertion
2. Add tests
