## `Array.every`

every跟some相反，some是只要有一个就行，every是要所有的为真才返回真

```js
const everyArr = [ false, true, false, false, true ]

// 三个参数：遍历项 索引 数组本身
// 配合箭头函数，需要所有为true，才返回true，否则返回false
const everyArr2 = everyArr.every((item, index, arr) => item)
console.log(everyArr2) // false

```

