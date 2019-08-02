# JavaScript Snippets

Table of Contents:

* [Factory Functions](#factory-functions)
* [Function with Optional Arguments](#function-with-optional-arguments)
* [Function with Optional Arguments and Defaults](#function-with-optional-arguments-and-defaults)

## Factory Functions

```js
const makePerson = ({ name }) => {
  const privateCreatedDate = new Date()
  // If argument is an object, copy it.
  // const thingCopy = { ...thing }
  return Object.freeze({
    talk () {
      console.log(`${name} says hello`)
    },

    changeName (newName) {
      name = newName
    },
    
    get createdAt () {
      return privateCreatedDate
    }
  })
}

const max = makePerson({ name: 'Max' })
max.talk() // -> 'Max says hello'

max.changeName('Maximilian')
max.talk() // -> 'Maximilian says hello'
console.log(max.createdAt) // -> 2019-08-01T23:56:36.232Z
```

* [Should You Use Classes in JavaScript?](https://medium.com/@vapurrmaid/should-you-use-classes-in-javascript-82f3b3df6195)
* [Elegant patterns in modern JavaScript: Ice Factory](https://medium.com/free-code-camp/elegant-patterns-in-modern-javascript-ice-factory-4161859a0eee)

## Function with Optional Arguments

```js
function (required, {optionalArg, optionalCallback} = {}) {
  // Function body here
}
```

## Function with Optional Arguments and Defaults

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
