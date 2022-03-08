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
function handleJimWork() {
  return new Promise((resolve, reject) => {
    // Slow method that runs in the background
    const success = doJimWork()
    if (success) {
      resolve(100)
    } else {
      reject("Jim broke his leg")
    }
  })
}

handleJimWork().then(amount => {
  console.log(`Jim paid you ${amount} dollars`)
}).catch(reason => {
  console.error(`Error: ${reason}`)
})
```

Promises are used when you need to invoke callbacks.

```js
Promise.all([promise1, promise2]).then(...)  

Promise.race([promise1, promise2]).then(...)
```
