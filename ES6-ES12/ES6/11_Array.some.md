## `Array.some`

some 意思就是只要有一个为真，那就返回真

```js
const someArr = [false, true, false, false, true]

// 三个参数：遍历项、索引、数组本身
// 配合箭头函数，只要有一个为true，就返回true，一个true都没有，就返回false
const someArr2 = someArr.some((item, index, arr) => item)
console.log(someArr2)
```

