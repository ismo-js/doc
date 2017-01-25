```
     ___          ____    _____    _   _    _ ___   _ ______
    / _ \        / ___⟩  |_   _|  | | | |  | ˇ__/  | ˇ      \
   ⟨ ⟨ ,⟩ ⟩       \__  \    | |    | `–´ |  | |     | ,^. ,^. |
    \_\_/        ⟨____/    |_|    `.___,´  |_|     |_| |_| |_|

```

- **`RAW`** numerischer Wert
- **`STR`** Stringwert
- **`RED`** Reduktionsfunktion
- **`ERR`** Fehler

## Map
```js
> new $(
    {
        [RAW]: raw,
    }=> raw * 0.01,
)::$(
    1,
    2,
    3,
    null,
)

$(RED=RAW*0.01|RAW=0.01)(RAW=0.02)(RAW=0.03)
```

## Map2
```js
> new $(
    {}=> 4,
)::$(
    1,
    2,
    3,
    null,
)

$(RED=4|RAW=4)(RAW=4)(RAW=4)
```

## Filter
```js
> new $()
```
