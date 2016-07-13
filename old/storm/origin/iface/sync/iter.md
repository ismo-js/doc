```js
> {
>   next: ()=> {done: true}
> }
[]

> (function* () {})()
[]

> {
>   [Symbol.iterator]: ()=> {
>     next: ()=> {done: true}
>   }
> }
[]
```
