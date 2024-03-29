---
id: 5900f4be1000cf542c50ffd0
title: 'Problem 337: Totient-Treppenstufen-Sequenzen'
challengeType: 1
forumTopicId: 301995
dashedName: problem-337-totient-stairstep-sequences
---

# --description--

Let $\\{a_1, a_2, \ldots, a_n\\}$ be an integer sequence of length $n$ such that:

- $a_1 = 6$
- for all $1 ≤ i &lt; n$ : $φ(a_i) &lt; φ(a_{i + 1}) &lt; a_i &lt; a_{i + 1}$

$φ$ bezeichnet die Eulersche Totalitätsfunktion.

Lasse $S(N)$ die Anzahl solcher Folgen mit $a_n ≤ N$ sein.

For example, $S(10) = 4$: {6}, {6, 8}, {6, 8, 9} and {6, 10}.

Wir können überprüfen, dass $S(100) = 482\\,073\\,668$ und $S(10\\,000)\bmod {10}^8 = 73\\,808\\,307$.

Find $S(20\\,000\\,000)\bmod {10}^8$.


# --hints--

`totientStairstepSequences()` should return `85068035`.

```js
assert.strictEqual(totientStairstepSequences(), 85068035);
```

# --seed--

## --seed-contents--

```js
function totientStairstepSequences() {

  return true;
}

totientStairstepSequences();
```

# --solutions--

```js
// solution required
```
