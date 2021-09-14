## `Array.filter`

```js
const filterArr = [1, 2, 3, 4, 5]

// 三个参数：遍历项 索引 数组本身
// 配合箭头函数，返回大于3的集合
const filterArr2 = filterArr.filter((item, index, arr) => item > 3)
console.log(filterArr2) //[4, 5]
```

