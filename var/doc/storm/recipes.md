```
     ___          ____    _____    _   _    _ ___   _ ______
    / _ \        / ___⟩  |_   _|  | | | |  | ˇ__/  | ˇ      \
   ⟨ ⟨ ,⟩ ⟩       \__  \    | |    | `–´ |  | |     | ,^. ,^. |
    \_\_/        ⟨____/    |_|    `.___,´  |_|     |_| |_| |_|

```

# Application of Sturm

## Properties
### Meta
- **`IDX`** Index of the event
- **`LEN`** Length of the stream
- **`KEY`** Key of the event
- **`PRE`** Previous result
- **`NXT`** Next event in the stream
- **`ERR`** Error

### Value
- **`RAW`** Numeric value
- **`STR`** String value
- **`FUN`** Function

## Recipes
### Map
```js
> new $(
    async {
        [RAW]: raw,
    }=> await raw * 0.01,
)(
    1,
    2,
    3,
)

${RAW:0.01}{RAW:0.02}{RAW:0.03}
```

### Map2
```js
> new $(
    async {}=> 4,
)(
    1,
    2,
    3,
)

${RAW:4}{RAW:4}{RAW:4}
```

### Filter
```js
> new $.when(
    async v=> await v > 0,
)(
    1,
    0,
    2,
    0,
)

${RAW:1}{RAW:2}
```

### Take
```js
> $.crop(
    async {
        [IDX]: idx
    }=> await idx < 3,
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
)

${STR:a}{STR:b}{STR:c}
```

### Drop
```js
> $.crop(
    async {
        [IDX]: idx
        [LEN]: len
    }=> await idx + 2 < await len,
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
)

${STR:a}{STR:b}{STR:c}{STR:d}
```

### Last
```js
> $.crop(
    async {
        [IDX]: idx
        [LEN]: len
    }=> await len - 2 < await idx,
)(
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
)

${STR:e}{STR:f}
```

### Start/w
```js
> new $(0)(...[1,2,3])

${RAW:0}{RAW:1}{RAW:2}{RAW:3}
```

### EndOn
```js
> $(
    async {end}=> crop(!await end),
)(
    {end: false},
    {end: true},
    {end: false},
)

${end:false}
```

### Fold
```js
> new $(
    {},
    async {
        [RAW]: raw,
        [PRE]: pre,
    }=> await raw * await pre,
)(1,2,3)

${RAW:1}{RAW:2}{RAW:6}
```

### Patch
```js
> new $(
    async {
        [ERR]: err,
        ...a,
    }=> await err ? null : a,
)(
    {data: "abc"},
    {[ERR]: new Error("Problem")}
)

${}
```
