# JavaScript Snippets

Table of Contents:

* [Factory Functions](#factory-functions)
* [Function Optional Defaults](#function-optional-defaults)

## Factory Functions

```js
const PersonFactory = (state) => {
  let name = state.name
  return {
    talk () {
      console.log(`${name} says hello`)
    },

    changeName (newName) {
      name = newName
    }
  }
}

const Grey = PersonFactory({ name: 'Grey' })
Grey.talk() // -> 'Grey'

Grey.changeName('Grey B')
Grey.talk() // -> 'Grey B'
```

Ref: [Should You Use Classes in JavaScript?](https://medium.com/@vapurrmaid/should-you-use-classes-in-javascript-82f3b3df6195)

## Function Optional Defaults

Where there are multiple optional function arguments:

```js
function (options) {
  const defaults = {
    enabled: true,
    action: 'update',
    isOwner: false,
    method: 'merge'
  }
  options = { ...defaults, ...options }

  // Function body here

}
```

_Bonus: The original object is copied and options is no longer a reference to the original options object._
