---
id: 5900f4051000cf542c50ff18
title: '问题 153：研究高斯整数'
challengeType: 1
forumTopicId: 301784
dashedName: problem-153-investigating-gaussian-integers
---

# --description--

As we all know the equation $x^2 = -1$ has no solutions for real $x$.

然而，如果我们引入虚数 $i$，则该等式具有两个解： $x = i$ 与 $x = -i$。

如果我们更进一步，方程式 ${(x - 3)}^2 = -4$ 有两个复数解： $x = 3 + 2i$ 和 $x = 3 - 2i$， 被称为共轭复数。

形式 $a + bi$ 的数字称为复数。

通常 $a + bi$ 与 $a − bi$ 为共轭复数。 高斯整数是指复数 $a + bi$，$a$ 与 $b$ 都是整数。

常规整数也是高斯整数（$b = 0$）。

为了将它们与 $b ≠ 0$ 的高斯整数区分开来，我们称这样的整数为“有理整数”。

一个高斯整数可以作为有理整数 $n$ 的约数，如果得到的余数也是一个高斯整数。

例如，如果我们将 5 除以 $1 + 2i$，我们可以通过以下方式进行简化：

将分子和分母乘以 $1 + 2i$ 的复共轭：$1 − 2i$。

结果是：

$$\frac{5}{1 + 2i} = \frac{5}{1 + 2i} \frac{1 - 2i}{1 - 2i} = \frac{5(1 - 2i)}{1 - {(2i)}^2} = \frac{5(1 - 2i)}{1 - (-4)} = \frac{5(1 - 2i)}{5} = 1 - 2i$$

所以 $1 + 2i$ 是 5 的约数.

请注意，$1 + i$ 不是 5 的除数，因为：

$$\frac{5}{1 + i} = \frac{5}{2} - \frac{5}{2}i$$

注意，如果高斯整数（$a + bi$）是有理整数 $n$ 的约数，则其共轭复数（$a − bi$）也是 $n$ 的因子。 事实上，5 有六个因数，使得实部为正数：{1, 1 + 2i, 1 − 2i, 2 + i, 2 − i, 5}。

以下是前五个正整数的所有约数表：

| n | 实数部分为正的高斯整数约数表                        | 这些除数的总和 s(n) |
| - | ------------------------------------- | ------------ |
| 1 | 1                                     | 1            |
| 2 | 1, 1 + i, 1 - i, 2                    | 5            |
| 3 | 1, 3                                  | 4            |
| 4 | 1, 1 + i, 1 - i, 2, 2 + 2i, 2 - 2i, 4 | 13           |
| 5 | 1, 1 + 2i, 1 - 2i, 2 + i, 2 - i, 5    | 12           |

对于实数部分为正的约数，我们有：$\displaystyle\sum_{n=1}^5 s(n) = 35$。

对于 $1 ≤ n ≤ {10}^5$, $\displaystyle\sum_{n = 1}^{{10}^5} s(n) = 17924657155$.

求 $\displaystyle\sum_{n=1}^{{10}^8} s(n)$?

# --hints--

`sumGaussianIntegers()` 应得 `17971254122360636`。

```js
assert.strictEqual(sumGaussianIntegers(), 17971254122360636);
```

# --seed--

## --seed-contents--

```js
function sumGaussianIntegers() {

  return true;
}

sumGaussianIntegers();
```

# --solutions--

```js
// solution required
```
