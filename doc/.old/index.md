```
    ___          ____    _____    _   _    _ ___   _ ______
   / _ \        / ___⟩  |_   _|  | | | |  | ˇ__/  | ˇ      \
  ⟨ ⟨ ,⟩ ⟩       \__  \    | |    | `–´ |  | |     | ,^. ,^. |
   \_\_/        ⟨____/    |_|    `.___,´  |_|     |_| |_| |_|

```

*Universal functional stream handling*

## Origins
### `tick$`
```
> tick$
@[t,t,t…>
```


## Mappings
### `x` *join*
```js
> @[
>   @[x=> x+1],
>   @[1,2,3],
> ]::x()
@[2,3,4]

> @[
>   @[-,x=> x+1,x=> x+2],
>   @[1,-,-,2],
> ]::x()
@[-,2,3,4]

> @[
>   @[to],
>   @[5],
>   @[a,-,b,d],
> ]::x()
@[5,-,5,5]

> @[
>   @[filter],
>   @[x=> a === x],
>   @[a,-,b,d],
> ]::x()
@[a,-,-,-]

> @[
>   @[when],
>   @[-,-,a,-,-,b],
>   @[1],
> ]::x()
@[-,-,1,-,-,1]
```

### `fold`
```js
> @[
>   8,
>   x=>x+1,
>   x=>x+2,
>   x=>x+1,
>   -,
>   x=>x+1,
> ]::fold()
@[8,9,11,12,-,13]
```


## Ranges
### `succ` *succeed*
```js
> @[
>   @[a,-,b,c,-],
>   @[-,-,-,d],
> ]::succ()
@[
  [a,-,b,c,-],
  [-,-,-,-,-,d],
]
```


## Finings
### `last`
```js
> @[1,2]::last()
@[-,-,2]
```

### `add`
```js
> @[
>   @[a,-,b],
>   @[c,d],
> ]::add()
@[a,c,d,b]
```


## Shortcuts
```js
b$::pre(a$) == @[a$, b$]::succ()::add()
b$::post(a$) == @[b$, a$]::succ()::add()
a$::scan(f$, seed) == [f$, a$]::x()::pre(@[seed])::fold()
```

//TODO how to take, drop, till, since?
//TODO logics
