# `subjects::filter()`

The same as `map`, but the return value isn't produced, but it's boolean value is used to decide if the original value should be left in the result stream or not.

### Example
```js
> [
>   [x=> x%2]::fill(),
>   [1,5,8],
> ]::filter()
[1,5,-]
```
