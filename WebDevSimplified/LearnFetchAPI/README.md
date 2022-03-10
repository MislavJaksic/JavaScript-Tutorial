## [Learn Fetch API In 6 Minutes](https://www.youtube.com/watch?v=cuEtnrL9-H0)

```js
fetch("https://example.com/users")
  .then(response => response.json())
  .then(jsonBody => console.log(jsonBody))

fetch("https://example.com/users", {
  method: "POST",
  body: JSON.stringify({ name: "Anne" }),
  headers: { "Content-Type": "application/json" }
})
```
