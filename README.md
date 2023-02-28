# Programming in なでしこ
[なでしこ3](https://github.com/kujirahand/nadesiko3) is an open-source programming language which aims to align with 
written Common Japanese and to be intuitive to people who know Common Japanese (For explanations on "Common Japanese," see 
[this article on Wikipedia](https://en.wikipedia.org/wiki/Japanese_language#Geographic_distribution)).

# HowTo
## Install
To install, get the [nvm](https://github.com/nvm-sh/nvm) and install the latest stable version of node.js.

Then run the following in your preferred directory:
```
yarn init
yarn add nadesiko3
```

## Run
To run, just execute your code as follows:

```
yarn cnako3 ./your-code.nako3
```

# Status
The current version of なでしこ is `3`.
As far as I know the implementation of this language heavily relies on transpilation to node.js (of latest stable node.js distribution).

## Notes
I reckon that the language has a lot of heavy snippets.
For example, the following code

`「プログラミングは面白い」と話す。`

Produces a (auto-generated) voice reading the given string (`プログラミングは面白い`) based on Common Japanese pronunciation,
and outputs it as a sound from the browser (This function `話す` seems to produce a sytax error when called in a CLI node environment).

## Subtle specs
Also, it might be slightly counter-intuitive to people living outside of Japan, since many features capture the subtle mistakes
that always catches Japanese newbies in programming.

For example, it seems that `1` (ASCII-compatible numeral, U+0031) and 
`１` (1, but takes up double space (="Full-Width") and only produced from Japanese input systems, U+FF11)
are treated as the same character in なでしこ3.

Similarly, some common Japanese-style arithmetic operators are interchangable with Python-style operators.

### Interchangeable operators

| Japanese style | Python3-style | Operation      |
| ---            | ---           | ---            |
| `＋`           | `+`           | Addition       |
| `−`            | `-`           | Subtraction    |
| `×`[^1]        | `*`           | Multiplication |
| `÷`[^2]        | `/`           | Division       |
| `％`           | `%`           | Modulus        |

Note that the multiplication operator `×` is the multiplication sign (U+00D7), not an `x` (the Latin small letter x, U+007F) nor `ｘ` 
(Full-Width x, U+FF58).


### NOT-alike operators
While in the case above Python3-style operators were accepted in なでしこ3, the following operators are not interchangable between なでしこ3
and Python.

| nako3 | Python | Operation            |
| ---   | ---    | ---                  |
| s & s | s + s  | String concatenation |
| 2^2   | 2\*\*2 | Power                |



[^1]: Not ✕ nor ✖ nor x because they are different characters (Rule of thumb would be not to use *機種依存文字*).
[^2]: Not ➗ because they are different characters (Rule of thumb would be not to use *機種依存文字*).
