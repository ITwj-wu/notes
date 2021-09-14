## `async await`

在工作中很常用的语法，**以同步方式执行异步操作**

平时可能会遇到这样的场景，接口一，请求到数据一，而数据一被当做请求二的参数去请求数据二，我们用Promise这样做

```js
function fn(){
    return new Promise((resolve,reject) => {
        setTimeout(() => {
            resolve(5)
        },1000)
    }).then(res => {
        new Promise((resolve,reject) => {
            setTImeout(() => {
                resolve(res * 10)
            },2000)
        }).then((sres) =>{
            console.log(sres)
        })
    })
}
fn() // 3秒后输出50
```

这样的嵌套不美观，如果有多个接口请求，这样会嵌套很多层，可以使用`async/await`来代替以同步方式执行异步

**注意**

- `await`只能在`async`函数里使用
- `await`后面最好接`Promise`,如果后面接普通函数则会直接执行
- `async`函数返回的是一个`Promise`

```js
function fn1(){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve(5)
        },1000)
    })
}

function fn2(data){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve(data*10)
        },2000)
    })
}

async function fn(){
    // 同步方式执行异步，像排队一样
    const data1 = await fn1() // 等待1秒后数据返回向下执行
    const data2 = await fn2(data1) // 拿data1去请求，两秒后数据返回，往下走
    console.log(data2) //总共三秒，输出50
}
fn()
```

