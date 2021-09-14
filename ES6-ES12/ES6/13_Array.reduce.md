## `Array.reduce`

- 第一个参数callback函数：pre为上次return的值，next为数组的本次遍历的项
- 第二个参数为初始值，也是第一个pre

```js
// 计算 1+2+3+4+5
const reduceArr = [1, 2, 3, 4, 5]
const sum = reduceArr.reduce((pro, next) => { 
    return pro + next 
}, 0 )
console.log(sum) // 15
```

统计元素出现个数

```js
const nameArr = ['wjj','sunshine','wjj','sunshine','hh','hh']
const totalObj = nameArr.reduce((pre, next) => {
    if(pre[next]){
        pre[next]++
    }else{
        pre[next] = 1
    }
    return pre
},{}) 
console.log(totalObj) // { 'wjj': 2, 'sunshine':2, 'hh':2 }
```



