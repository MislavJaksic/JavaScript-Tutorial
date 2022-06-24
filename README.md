## JavaScript Tutorial

### Destructuring assignment

```
let [name1, name2, ...titles] = ["Julius", "Caesar", "Consul", "of the Roman Republic"];
// name1 = "Julius"
// name2 = "Caesar"
// titles = ["Consul", "of the Roman Republic"]

function showMenu({title = "Untitled", width = 200, height = 100, items = []}) {...}
let options = {title: "My menu", items: ["Item1", "Item2"]};
```

### Export and Import

`export default`:
* `export` allows `import`
* `default` allows `import` without `{}`

### Promise

You can't extract data synchronously from an asynchronour Promise.  
You can however use `async`/`await` to make asynchronous code look like synchronous code.  