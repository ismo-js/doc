# `subjects::dispose()`

Produces each stream of `subjects`. At points of time where there are values in multiple `subjects`, it buffers the value of the later stream and produces it at a point of time where no `subject` produces.

### Example
```js
> [
>   [-,a,b,-,-,-,b],
>   [-,a,c,-,-,-,b],
> ]::dispose()
[
  [-,a,-,b,-,-,b],
  [-,-,a,-,c,-,-,b],
]
```
