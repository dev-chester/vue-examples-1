# [Vue Events](https://vuejs.org/v2/guide/events.html)

This demonstrates event functionality. Events are spawned
and handled with popups in the browser.

## Usage

```javascript
var example1 = new Vue({
    el: '#example-1',
    data: {
    counter: 0
    }
})

var example2 = new Vue({
    el: '#example-2',
    data: {
    name: 'Vue.js'
    },
    // define methods under the `methods` object
    methods: {
    greet: function(event) {
        // `this` inside methods points to the Vue instance
        alert('Hello ' + this.name + '!')
        // `event` is the native DOM event
        if (event) {
        alert(event.target.tagName)
        }
    }
    }
})

new Vue({
    el: '#example-3',
    methods: {
    say: function(message) {
        alert(message)
    },
    warn: function(message, event) {
        // now we have access to the native event
        if (event) event.preventDefault()
        alert(message)
    }
    }
})
```

```html
  <div id="example-1">
    <button v-on:click="counter += 1">Add 1</button>
    <p>The button above has been clicked {{ counter }} times.</p>
  </div>
  <div id="example-2">
    <!-- `greet` is the name of a method defined below -->
    <button v-on:click="greet">Greet</button>
  </div>
  <div id="example-3">
    <button v-on:click="say('hi')">Say hi</button>
    <button v-on:click="say('what')">Say what</button>
    <button v-on:click="warn('Form cannot be submitted yet.', $event)">
      Submit
    </button>
    <!-- same as above -->
    <input v-on:keyup.enter="say('submitted')">
  </div>
```

## Demo

[https://peterlamar.github.io/vue-examples/events/](https://peterlamar.github.io/vue-examples/events/)

[code sandbox](https://codesandbox.io/s/pmo03ppvl0)

## Demo locally

Open file index.html in a web browser
