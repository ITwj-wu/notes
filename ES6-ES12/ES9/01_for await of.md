## `for await of`

场景

```js
function fn(time){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve(`${time}毫秒后成功！`)
        },1000)
    })
}
fn(3000).then(res => console.log(res))
fn(1000).then(res => console.log(res))
fn(2000).then(res => console.log(res))

// 输出结果
// 1000毫秒后成功！
// 2000毫秒后成功！
// 3000毫秒后成功！
```

想要的输出结果：

```js
// 3000毫秒后成功！
// 1000毫秒后成功！
// 2000毫秒后成功！
```

想到用`async/await`

```js
function fn(time){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve(`${time}毫秒后成功！`)
        },1000)
    })
}

async function asyncFn(){
    const data1 = await fn(3000)
    console.log(data1) // 3秒后输出 3000毫秒后成功！
    const data2 = await fn(1000)
    console.log(data2) // 再过1秒输出 1000毫秒后成功！
    const data3 = await fn(2000)
    console.log(data3) // 再过2秒输出 2000毫秒后成功！
} 
asyncFn()
```

那如果有几十个呢？那就要写几十个await，有没有什么方法可以循环输出呢？这时就要用`for await of`

```js
function fn(time){
    return new Promise((resolve,reject)=>{
        setTimeout(()=>{
            resolve(`${time}毫秒后成功！`)
        },1000)
    })
}
async function asyncFn(){
    const arr = [fn(3000), fn(1000), fn(2000), fn(3000)]
    for await (let res of arr){
        console.log(res)
    }
}
// 3000毫秒后成功！
// 1000毫秒后成功！
// 2000毫秒后成功！
// 3000毫秒后成功！
```

 