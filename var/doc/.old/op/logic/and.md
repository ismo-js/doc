# `subjects::and()`

Produces each stream of `subjects`, but each of them itself only produce a value when *all* other `subjects` produce something at the same time. When *one* `subject` ends, every stream ends.

### Example
```js
> [
>   [a,b,c,-,a,b,c],
>   [b,b,-,d,b,-,d,b],
> ]::and()
[
  [a,b,-.-,a,-,c],
  [b,b,-,-,b,-,d],
]

// how to map to constant value
> [[a]::fill(), x]::and()[0]
x’ // x, but all values replaced with a
```
