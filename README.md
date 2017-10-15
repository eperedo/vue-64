# vue-six-four

> vue 2.x.x component which generate base64 from a file [Demo](https://codesandbox.io/s/94nzlkwn1o)

![Demo vue-64](https://user-images.githubusercontent.com/461124/31588306-7eb461fc-b1b5-11e7-96ab-27fe12905330.png)

### Install

npm install vue-six-four --save

### Usage

```js
import VueSixFour from 'vue-six-four';
```

```js
// Include as a component
{
  components: {
    VueSixFour,
  },
  methods: {
    getFileInfo(file) {
      console.log('File Information', file);
    },
  },
}

```

```html
<vue-six-four v-on:vue-six-four="getFileInfo">
```

In this event you can get the information of the whole file.

```json
{
  "lastModified": 1491695457000,
  "lastModifiedDate" : "Sat Apr 08 2017 18:50:57 GMT-0500 (-05)",
  "name" : "fileName.jpg",
  "size" : "14361",
  "type" : "image/jpeg",
  "sixFour": "really long base64 here"
}
```

### Multiple Files

By default the component only allows to select one file, but you can change that using the allow-multiple
prop.

```html
<vue-six-four v-on:vue-six-four="getFileInfo" v-bind:allow-multiple="true">
```

The only difference is the event now return an array instead an object.

## Build Setup

``` bash
# install dependencies
npm install

# build component using poi
npm run component

```
