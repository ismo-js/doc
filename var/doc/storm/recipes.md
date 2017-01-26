```
     ___          ____    _____    _   _    _ ___   _ ______
    / _ \        / ___⟩  |_   _|  | | | |  | ˇ__/  | ˇ      \
   ⟨ ⟨ ,⟩ ⟩       \__  \    | |    | `–´ |  | |     | ,^. ,^. |
    \_\_/        ⟨____/    |_|    `.___,´  |_|     |_| |_| |_|

```

- **`IDX`** Index of the event
- **`LEN`** Length of the stream
- **`KEY`** Key of the event
- **`ERR`** Error
- **`RAW`** Numeric value
- **`STR`** String value
- **`FUN`** Function

## Map
```js
> new $(
    async {
        [RAW]: raw,
    }=> await raw * 0.01,
)(
    1,
    2,
    3,
    null,
)

$(RAW=0.01)(RAW=0.02)(RAW=0.03)
```

## Map2
```js
> new $(
    async {}=> 4,
)(
    1,
    2,
    3,
    null,
)

$(RAW=4)(RAW=4)(RAW=4)
```

## Filter
```js
> new $(
    async v=> when(await v > 0),
)(
    1,
    0,
    2,
    0,
    null,
)

$(RAW=1)(RAW=2)
```

## Take
```js
> new $(
    async {
        [IDX]: idx
    }=> crop(await idx < 3),
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
    null,
)

$(STR=a)(STR=b)(STR=c)
```

## Drop
```js
> new $(
    async {
        [IDX]: idx
        [LEN]: len
    }=> crop(await idx + 2 < await len),
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
    null,
)

$(STR=a)(STR=b)(STR=c)(STR=d)
```

## Last
```js
> new $(
    async {
        [IDX]: idx
        [LEN]: len
    }=> crop(await len - 2 < await idx),
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
    null,
)

$(STR=e)(STR=f)
```

## Start/w
```js
> new $(0)(...[1,2,3])

$(RAW=0)(RAW=1)(RAW=2)(RAW=3)
```

## EndOn
```js
```
