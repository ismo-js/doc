# `subjects::xor()`

Produces each stream of `subjects`, but each of them itself only produce a value when *no* other `subject` produces something at the same time.

### Example
```js
> [
>   [a,-,b,c],
>   [p,-,-,q,r],
> ]::xor()
[
  [-,-,b,-],
  [-,-,-,-,r],
]
```
