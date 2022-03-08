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
  console.log(msg)
  console.log("First Timeout")
  return setTimeoutPromise(500)  // need to return it to b able to chain .then
}).then(msg => {
  console.log(msg)
  console.log("Second Timeout")
})
// Output:
// You waited 250 milliseconds
// First Timeout
// You waited 500 milliseconds
// Second Timeout
```

```js
doStuff()
async function doStuff() {
	try {
		  const msg1 = await setTimeoutPromise(250)  // do something else until this Promise resolves, then continue executing code
		  console.log(msg1)
		  console.log("First Timeout")

		  const msg2 = await setTimeoutPromise(500)
		  console.log(msg2)
		  console.log("Second Timeout")
		} catch (error) {
			console.log(error)
		}
}
// Output:
// You waited 250 milliseconds
// First Timeout
// You waited 500 milliseconds
// Second Timeout
```