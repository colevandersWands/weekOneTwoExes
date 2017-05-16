### last

write a function called last that takes one argument, an object, and returns an object containing only the last key/value pair and does NOT modify the original object.
(aka without side effects, nothing in the global scope has been modified)

```jsx
var obj = {a: 1, b: 2}

var newObje = last(obj)
newObje // {b: 2}
obj // {a: 1, b: 2}
```