# `subjects::map()`

Applies `subject[0][x]` to `subject[1][x]`; applies the resulting function on `subject[2][x]`… Produces the final results of these applications and `NIL` at points of time where not all values are given. Ends when a value gets mapped to `FIN`.

### Example
```js
> [
>   [(x,y)=> x]::fill(),
>   [a,b],
>   [-,c,d],
> ]::map()
[-,b]
```
