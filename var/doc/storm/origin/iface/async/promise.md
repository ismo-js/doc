```js
> new Promise(rsv=> {
>   setInterval(()=> rsv(true), 1234)
> })
[-…,true]
```
