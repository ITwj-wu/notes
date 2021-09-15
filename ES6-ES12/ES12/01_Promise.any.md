## `Promise.any`

ES12新增`Promise`方法

- 接收一个`Promise`数组，数组中如有非`Promise项`，当此项成功
- 如果有一个Promise成功，返回这个成功结果
- 如果所有`Promise`失败，则报错

```js
function fn(time, isResolve) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      isResolve ? resolve(`${time}毫秒后我成功啦！！！`) : reject(`${time}毫秒后我失败啦！！！`)
    }, time)
  })
}

// 当有成功的时候，返回最快那个成功
Promise.any([fn(2000, true), fn(3000), fn(1000, true)]).then(res => {
  console.log(res) // 1秒后 输出  1000毫秒后我成功啦
}, err => {
  console.log(err)
})

//当全部失败时
Promise.any([fn(2000), fn(3000), fn(1000)]).then(res => {
  console.log(res)
}, err => {
  console.log(err) // 3秒后 报错 all Error
})
```

