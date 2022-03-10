## [JavaScript Promises In 10 Minutes](https://www.youtube.com/watch?v=DHvZLI7Db8E)

```js
let p = new Promise((resolve, reject) => {
	let a = 1 + 1
	if (a == 2) {
		resolve("Success")
	} else {
		reject("Failed")
	}
})

p.then((message) => console.log(`Displays Success: ${message}`))
 .catch((message) => console.log(`Displays Failed: ${message}`))
```

```js
function handleWork() {
  return new Promise((resolve, reject) => {
    const success = doWork()  // Slow method that runs in the background
    if (success) {
      resolve(100)
    } else {
      reject("Cannot do work")
    }
  })
}

handleWork().then(amount => {
  console.log(`You were paid ${amount} dollars`)
}).catch(reason => {
  console.error(`Error: ${reason}`)
})
```

Promises are used when you need to invoke callbacks.

```js
Promise.all([promise1, promise2]).then(...)  

Promise.race([promise1, promise2]).then(...)
```
