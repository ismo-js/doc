# `subjects::succeed()`

Produces each stream of `subjects`, but each of them starts not until the stream *before* has finished.

### Example
```js
> [
>   [a,b,a],
>   [b,a,b],
>   [a,b,a],
> ]::succeed()
[
  [a,b,a],
  [-,-,-,b,a,b],
  [-,-,-,-,-,-,a,b,a],
]

// how to eliminate pauses between values
> [x,x]::succeed()[1]
x’ //x, but all values succeeding each other directly.
```
