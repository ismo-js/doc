```js
> new Emitter(
>   pdc=> setInterval(()=> pdc(true), 1234),
>   id=> clearInterval(id)
> )
[-…,true,-…,true…]
``
