# `subjects::unique()`

Produces each `subject`, but each of them itself only produce the value at a specific point of time if it's unique compared to all other values at the given point of time.

### Example
```js
> [
>   [a,-,b,c],
>   [b,-,-,c,a],
> ]::unique()
[
  [a,-,b,-],
  [b,-,-,-,a],
]
``
