# `subjects::combine()`

Produces a value when *any* of the `subjects` produces. When there are multiple values at the same point of time, the first `subject` wins. Ends when *all* `subjects` end.

### Example
```js
> [
>   [-,a,b],
>   [-,-,p,q],
> ]::combine()
[-,a,b,q]

// how to resolve promises
> [pr1, pr2]::dispose()::combine()
[-,-,-,result[pr1],result[pr2]]
```
