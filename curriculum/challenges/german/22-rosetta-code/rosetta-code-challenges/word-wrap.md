---
id: 594810f028c0303b75339ad4
title: Zeilenumbruch
challengeType: 1
forumTopicId: 302344
dashedName: word-wrap
---

# --description--

Even today, with proportional fonts and complex layouts, there are still cases where you need to wrap text at a specified column. The basic task is to wrap a paragraph of text in a simple way.

# --instructions--

Schreibe eine Funktion, die diesen Text in eine beliebige Anzahl von Zeichen umbrechen kann. Ein Beispiel: Der auf 80 Zeichen umbrochene Text sollte wie folgt aussehen:

<pre>
Wrap text using a more sophisticated algorithm such as the Knuth and Plass TeX
algorithm. If your language provides this, you get easy extra credit, but you
must reference documentation indicating that the algorithm is something better
than a simple minimum length algorithm.
</pre>

# --hints--

wrap sollte eine Funktion sein.

```js
assert.equal(typeof wrap, 'function');
```

wrap sollte einen String zurückgeben.

```js
assert.equal(typeof wrap('abc', 10), 'string');
```

wrap(80) sollte 4 Zeilen zurückgeben.

```js
assert(wrapped80.split('\n').length === 4);
```

Deine `wrap` Funktion sollte unseren erwarteten Text zurückgeben.

```js
assert.equal(wrapped80.split('\n')[0], firstRow80);
```

wrap(42) sollte 7 Zeilen zurückgeben.

```js
assert(wrapped42.split('\n').length === 7);
```

Deine `wrap` Funktion sollte unseren erwarteten Text zurückgeben.

```js
assert.equal(wrapped42.split('\n')[0], firstRow42);
```

# --seed--

## --after-user-code--

```js
const text =
`Wrap text using a more sophisticated algorithm such as the Knuth and Plass TeX algorithm.
If your language provides this, you get easy extra credit,
but you ''must reference documentation'' indicating that the algorithm
is something better than a simple minimum length algorithm.`;

const wrapped80 = wrap(text, 80);
const wrapped42 = wrap(text, 42);

const firstRow80 =
    'Wrap text using a more sophisticated algorithm such as the Knuth and Plass TeX';

const firstRow42 = 'Wrap text using a more sophisticated';
```

## --seed-contents--

```js
function wrap(text, limit) {
  return text;
}
```

# --solutions--

```js
function wrap(text, limit) {
  const noNewlines = text.replace('\n', '');
  if (noNewlines.length > limit) {
    // find the last space within limit
    const edge = noNewlines.slice(0, limit).lastIndexOf(' ');
    if (edge > 0) {
      const line = noNewlines.slice(0, edge);
      const remainder = noNewlines.slice(edge + 1);
      return line + '\n' + wrap(remainder, limit);
    }
  }
  return text;
}
```
