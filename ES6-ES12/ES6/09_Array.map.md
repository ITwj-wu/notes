## `Array.map`

```js
const mapArr = [1, 2, 3, 4, 5]

// 三个参数：遍历项 索引 数组本身
// 配合箭头函数，对每一个元素进行翻倍
mapArr.map((item, index, arr) => item * 2 )
console.log(mapArr) // [1, 4, 6, 8, 10]
```

