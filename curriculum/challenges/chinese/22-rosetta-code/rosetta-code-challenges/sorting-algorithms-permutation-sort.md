---
id: 5a23c84252665b21eecc800c
title: 排序算法/排列排序
challengeType: 1
forumTopicId: 302316
dashedName: sorting-algorithmspermutation-sort
---

# --description--

Write a function to implement a permutation sort, which proceeds by generating the possible permutations of the input array until discovering the sorted one. The function should return the sorted array.

伪代码：

<pre><b>while not</b> InOrder(list) <b>do</b>
  nextPermutation(list)
<b>done</b>
</pre>

# --hints--

`permutationSort` 应该是一个函数。

```js
assert(typeof permutationSort == 'function');
```

`permutationSort([25, 32, 12, 7, 20])` 应该返回一个数组。

```js
assert(Array.isArray(permutationSort([25, 32, 12, 7, 20])));
```

`permutationSort([25, 32, 12, 7, 20])` 应该返回 `[7, 12, 20, 25, 32]`。

```js
assert.deepEqual(permutationSort([25, 32, 12, 7, 20]), [7, 12, 20, 25, 32]);
```

`permutationSort([38, 45, 35, 8, 13])` 应该返回 `[8, 13, 35, 38, 45]`。

```js
assert.deepEqual(permutationSort([38, 45, 35, 8, 13]), [8, 13, 35, 38, 45]);
```

`permutationSort([43, 36, 20, 34, 24])` 应该返回 `[20, 24, 34, 36, 43]`。

```js
assert.deepEqual(permutationSort([43, 36, 20, 34, 24]), [20, 24, 34, 36, 43]);
```

`permutationSort([12, 33, 26, 18, 1, 16, 38])` 应该返回 `[1, 12, 16, 18, 26, 33, 38]`。

```js
assert.deepEqual(permutationSort([12, 33, 26, 18, 1, 16, 38]), [
  1,
  12,
  16,
  18,
  26,
  33,
  38
]);
```

`permutationSort([3, 39, 48, 16, 1, 4, 29])` 应该返回 `[1, 3, 4, 16, 29, 39, 48]`。

```js
assert.deepEqual(permutationSort([3, 39, 48, 16, 1, 4, 29]), [
  1,
  3,
  4,
  16,
  29,
  39,
  48
]);
```

# --seed--

## --seed-contents--

```js
function permutationSort(arr) {

}
```

# --solutions--

```js
function permutationSort(arr) {
  function pSort(a) {
    var list = [];
    permute(a, a.length, list);
    for (var i = 0; i < list.length; i++) {
      var x = list[i];
      if (isSorted(x)) return x;
    }
    return a;
  }

  function permute(a, n, list) {
    if (n === 1) {
      var b = a.slice();
      list.push(b);
      return;
    }
    for (var i = 0; i < n; i++) {
      swap(a, i, n - 1);
      permute(a, n - 1, list);
      swap(a, i, n - 1);
    }
  }

  function isSorted(a){
    for(let i = 0; i < a.length - 1; i++)
      if(a[i] > a[i + 1])
        return false;
    return true;
  }

  function swap(arr, i, j) {
    var temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
  }
  return pSort(arr);
}
```
