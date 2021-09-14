## `for in`和`for of`

- `for in`可遍历对象和数组
- `for of`只能遍历数组，不能遍历对象

```js
// 先看for in
const obj = { name: 'wjj', age: 20, gender: '女' }
const arr = [1, 2, 3, 4, 5]

for(let key in obj){
    console.log(key) // name age gender
}

for(let index in arr){
    console.log(item) // 0 1 2 3 4 
}

//在看for of
for(let item of arr){
    console.log(item) // 1 2 3 4 5
}
```



