# `subject::fill()`

Produces the latest value till the next value arrives and never ends.

### Example
```js
> [a,-,-,b,c,-,-]::fill()
[a,a,a,b,c,c…>

> [a,b,c,d,e]::fill()
[a,b,c,d,e,e…>

> []::fill()
[-> //endless stream

// how to loop a stream
> [[a,b,c]]::fill()::succeed()::combine()
[a,b,c,a,b,c…>
```
