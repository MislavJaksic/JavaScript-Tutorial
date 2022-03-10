## [JavaScript Async Await](https://www.youtube.com/watch?v=V_Kr9OSfDeU)

```js
function setTimeoutPromise(delay) {
  return new Promise((resolve, reject) => {
    if (delay < 0) return reject("Delay must be greater than 0")

    setTimeout(() => {
      resolve(`You waited ${delay} milliseconds`)
    }, delay)
  })
}

setTimeoutPromise(250).then(msg => {
  console.log(`First Timeout: ${msg}`)
  return setTimeoutPromise(500)  // need to return it to be able to chain .then
}).then(msg => {
  console.log(`Second Timeout: ${msg}`)
})
// First Timeout: You waited 250 milliseconds
// Second Timeout: You waited 500 milliseconds
```

```js
async function doStuff() {
	try {
		  const msg1 = await setTimeoutPromise(250)  // do something else until this Promise resolves, then continue executing code; similar to yield in Python
		  console.log(`First Timeout: ${msg}`)

		  const msg2 = await setTimeoutPromise(500)
		  console.log(`Second Timeout: ${msg}`)
		} catch (error) {
			console.log(error)
		}
}
doStuff()
// First Timeout: You waited 250 milliseconds
// Second Timeout: You waited 500 milliseconds
```
