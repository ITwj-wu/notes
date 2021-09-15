## `Promise.allSettled`

新增`Promise`的方法

- 接收一个`Promise`数组，数组中如果有非`Promise`项，则此项当做成功
- 把每一个`Promise`结果，集合成数组，返回

```js
function fn(time, isResole){
    return new Promise ((resolve, reject)=>{
        setTimeout(()=>{
            isResolve ? resolve(`${time}毫秒后成功了！`) : reject(`${time}毫秒后失败了`)
        })
    })
}
Promise.allSettled([fn(2000, true), fn(1000), fn(3000)]).then(res => {
    console.log(res)
})
//三秒后输出
[
    { status: 'fulfilled', value: '2000毫秒后成功了！' },
    { status: 'rejected', reason: '1000毫秒后我失败了！' },
    { status: 'rejected', reason: '3000毫秒后我失败了！' },
]
```

