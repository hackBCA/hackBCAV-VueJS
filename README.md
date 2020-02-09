# A (briefish) intro to VueJS

hackBCA V, 2020

Aidan Glickman

[aidg.dev](http://aidg.dev)

## `$ wtf vue`

```sh
$ wtf vue
VUE: a progressive framework for building user interfaces
```

Essentially, it is a really popular javascript framework for building UIs and frontend apps.

## `requirements`

### `knowledge`

![Knowledge](https://thumbs.gfycat.com/EsteemedInconsequentialBuckeyebutterfly-size_restricted.gif)

If you are taking this course, I assume you have some basic web development knowledge. Specifically, I assume you possess the following skills:

- HTML
  - Vue components essentially look like glorified HTML, so this will be crucial
- **NOT STRICTLY NECESSARY:** CSS
  - We are going to want to make our websites pretty, so you are going to want to know CSS (I will probably be using SCSS during this course, but you should be able to understand fine just knowing CSS)
- JS
  - Know the fundamentals (conditionals, data types, arrays, objects, etc.)
  - **NOT STRICTLY NECESSARY:** There will be ES6 syntax in this course, so that would be useful as well (and arrow functions)
  - **NOT STRICTLY NECESSARY:** `async/await`? Might not get to this, but it will change the way you use javascript and is a good thing to learn

### `tools`

To go through this course, you will need to have a few things installed ahead of time.

- [nodeJS](https://nodejs.org/en/)
  - :black_square_button: If you are on Windows then download it from the website. (You could also use something like Chocolatey if you are in to that.)
  - :apple: If you are on MacOS I highly recommend using [homebrew](https://brew.sh/) and running `brew install node`
  - :penguin: If you are on linux just install from your package manager
    - :small_red_triangle: Arch: `pacman -S nodejs npm`
    - :red_circle: Ubuntu: `apt install -y nodejs`
    - :fish: Gentoo: Lol you don't need my help (`emerge nodejs`)
- **OPTIONAL:** [Yarn](https://classic.yarnpkg.com/en/)

  - I just prefer `yarn` to `npm` for package management, but it isn't required. Any `yarn` commands used in this documentation can be replaced with their `npm` equivalents.

- [Vue devtools](https://github.com/vuejs/vue-devtools)

  - Install the relevant extension for whatever browser you use
    - :radioactive: [Chrome Extension](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
    - :fire: [Firefox Addon](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
    - If you don't use Firefox or something Chromium based, then you can also use the [standalone electron app](https://github.com/vuejs/vue-devtools/blob/dev/packages/shell-electron) (Looking at you, guy who thinks he's cool because he uses QuteBrowser)

- [VueCLI](https://cli.vuejs.org/)
  - This is the tool we will use to generate all of the boilerplate for our Vue projects
  - install with `yarn global add @vue/cli` or `npm i -g @vue.cli` if you didn't install yarn

## `intro`

### `$ diff vue {everythingelse}`

Why are we learning Vue instead of another framework like React or Angular?

1. Lower learning curve than other frameworks
1. Really fast and light
1. Increasingly popular
1. I'm better at it

### `structure`

If you have learned basic web development in the past, you may remember the "Seperation of Concerns" paradigm, where you split up your HTML, CSS, and JS in to different files. Throw that idea away. Now. :smile:

#### `components`

![Component Graph](https://vuejs.org/images/components.png)

VueJS works on the "component" model, where instead of seperating things based on their function (layout, style, control) we seperate things in to little chunks called components, which we can often reuse.

Components have each of the three things we use in a web app within them, making them portable and easy to edit. Here is what a basic Vue component looks like:

```html
<template>
  <h1>Hi! I'm a Vue component called {{title}}!</h1>
</template>

<script>
  export default {
    name: 'Example Vue Component',
    props: ['title'],
  };
</script>

<style lang="scss" scoped>
  h1 {
    color: red;
  }
</style>
```

For a full Vue app, we are essentially just sticking a bunch of components together with some overhead to make a complete app.
