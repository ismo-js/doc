# `subject::blank()`

Returns `true` if the stream is blank. A blank stream ends immediately.

### Example
```js
> {length: 0}::blank()
true

> []::blank()
true
```
