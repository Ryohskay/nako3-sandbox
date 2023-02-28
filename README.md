# Programming in なでしこ
[なでしこ3](https://github.com/kujirahand/nadesiko3) is an open-source programming language which aims to align with 
written Common Japanese and to be intuitive to people who know Common Japanese (For explanations on "Common Japanese," see 
[this article on Wikipedia](https://en.wikipedia.org/wiki/Japanese_language#Geographic_distribution)).

# Status
The current version of なでしこ is `3`.
As far as I know the implementation of this language heavily relies on transpilation to node.js (of latest stable node.js distribution).

## Notes
I reckon that the language has a lot of heavy snippets.
For example, the following code

`「プログラミングは面白い」と話す。`

Produces a (auto-generated) voice reading the given string (`プログラミングは面白い`) based on Common Japanese pronunciation,
and outputs it as a sound from the browser (This function `話す` seems to produce a sytax error when called in a CLI node environment).
