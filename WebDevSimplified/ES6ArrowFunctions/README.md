## [JavaScript ES6 Arrow Functions Tutorial](https://www.youtube.com/watch?v=h33Srr5J9nY)

### Convert functions to arrow functions

```js
function sum(a, b) {
  return a + b
}
let sumAR = (a, b) => a + b

function isPositive(number) {
  return number >= 0
}
let isPositiveAR = (number) => number >= 0

function randomNumber() {
  return Math.random()
}
let randomNumberAR = () => Math.random()

document.addEventListener('click', function() {
  console.log('Click')
})
document.addEventListener('click', () => console.log('Click'))
```

### Scope differences

```js
class Person {
  constructor(name) {
    this.name = name
  }

  printNameArrow() {
    setTimeout(() => console.log(`Arrow: ${this.name}`), 100)
  }

  printNameFunction() {
    setTimeout(function() {console.log(`Function: ${this.name}`)}, 100)
  }
}

const person = new Person('Anne')
person.printNameArrow()  // Arrow: Anne
person.printNameFunction()  // Function:
```