## `Array.forEach`

ES6新增数组遍历方法

```js
const arr = [1, 2, 3, 4, 5]

//三个参数：遍历项、索引、数组本身
//配合箭头函数
arr.forEach((item, index, arr)=>{
    console.log(item, index, arr)
})
1 0 [ 1, 2, 3, 4, 5 ]
2 1 [ 1, 2, 3, 4, 5 ]
3 2 [ 1, 2, 3, 4, 5 ]
4 3 [ 1, 2, 3, 4, 5 ]
5 4 [ 1, 2, 3, 4, 5 ]
```



