# `subjects::cross()`

Produces a stream at any point of time where at least one `subject` has a value. Each of these stream contains the value of all `subjects` at this specific point of time.

### Example
```js
> [
>   [a,b,a]
>   [c,d,d],
>   [e,e,f,g],
> ]::cross()
[
  [a,c,e],
  [b,d,e],
  [a,d,f],
  [-,-,g],
]
``
