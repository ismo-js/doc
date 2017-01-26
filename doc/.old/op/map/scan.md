# `subjects::scan(initial)`

The same as `map`, but finally applies the result of `subject[n-1][x](subject[n][x])` on the final result of the application at the last point of time. If this memorized result isn't given, `scan` starts out with `initial`. Ignores points of time where not all values are given. Ends when the shortest `subject` ends.

#### Example
```js
> [
>   [(n, o)=> n+o]::fill(),
>   [1,2,3],
> ]::scan(1)
[2,4,7]
```
