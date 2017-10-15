# vue-six-four

> vue 2.x.x component which generate base64 from a file

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

## Build Setup

``` bash
# install dependencies
npm install

# build component using poi
npm run component

```
