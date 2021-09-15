## `Promise.finally`

新增Promise方法，无论失败或者成功状态，都会执行这个函数

```js
new Promise((resolve,reject)=>{
    resolve('成功')
}).then(
    res => { console.log(res) },
    err => { console.log(err) }
).finally(()=>{ console.log('俺是finally呀') })
```

