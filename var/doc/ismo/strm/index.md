# Map
## `x` *cross*
```js
> [
>   [a,-,-,-,b,-,c],
>   [-,-,d,-,-,e,f],
> ]::x()
[
  -,
  -,
  [a,d],
  -,
  [b,d],
  [d,e],
  [c,f],
]
```

## `map`
```js
> [1,2,3]::map([x=> x+1])
[2,3,4]

> [1,-,-,2]::map([-,x=> x+1,x=> x+2])
[-,2,3,4]

> [a,-,b,d]::map(val(5))
[5,-,5,5]
```
## `filter`
## `fold`

# Range
* **`fill`**
* **`take`**
* **`drop`**

# Fin
* **`last`**
* **`flat`**

# Other
* **`when`**
* **`pipe`**
