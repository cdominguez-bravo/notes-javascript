# JavaScript Snippets

Table of Contents:

* [Factory Functions](#factory-functions)

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
