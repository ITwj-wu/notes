## `Promise`

`promise`，中文名为承诺，承诺在哪呢？一旦他的状态改变，就不会再改。这里就介绍基本使用

基本使用

- 成功状态

```js
function requestData(){
    //模拟请求
    return new Promise((resolve, reject)=>{
        setTimeout(()=>{
            resolve('wjj')
        },1000)
    })
}

requestData().then((res)=>{
    console.log(res)   // 一秒后输出'wjj'
},err=>{
	console.log(err)
})
```

- 失败状态

```js
function requestData(){
    //模拟请求
    return new Promise((resolve, reject)=>{
        setTimeout(()=>{
            reject('出错啦！')
        },1000)
    })
}

requestData().then((res)=>{
    console.log(res)   
},err=>{
	console.log(err) // 一秒后输出 '出错啦！'
})
```

- all方法
  1. 接收一个Promise数组，数组中如果有非Promise项，则此项当做成功
  2. 如果所有的Promise都成功，则返回成功结果数组
  3. 如果有一个promise失败，则返回这个失败结果

```js 
// 如果全都为成功
function fn(time) {
  return new Promise((resolve, reject) => {
    console.log(88)
    setTimeout(() => {
      resolve(`${time}毫秒后我成功啦！！！`)
    }, time)
  })
}

Promise.all([fn(2000), fn(3000), fn(1000)]).then(res => {
  // 3秒后输出 [ '2000毫秒后我成功啦！！！', '3000毫秒后我成功啦！！！', '1000毫秒后我成功啦！！！' ]
  console.log(res) 
}, err => {
  console.log(err)
})



// 如果有一个失败
function fn(time, isResolve) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      isResolve ? resolve(`${time}毫秒后我成功啦！！！`) : reject(`${time}毫秒后我失败啦！！！`)
    }, time)
  })
}

Promise.all([fn(2000, true), fn(3000), fn(1000, true)]).then(res => {
  console.log(res)
}, err => {
  console.log(err) // 3秒后输出 '3000毫秒后我失败啦！！！'
})
```

- race方法
  1. 接收一个Promise数组，数组中如有非Promise项，则此项当做成功
  2. 哪个Promise最快得到结果，就返回那个结果，无论成功失败

```js
function fn(time, isResolve) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      isResolve ? resolve(`${time}毫秒后我成功啦！！！`) : reject(`${time}毫秒后我失败啦！！！`)
    }, time)
  })
}

Promise.race([fn(2000, true), fn(3000), fn(1000)]).then(res => {
  console.log(res)
}, err => {
  console.log(err) // 1秒后输出
})
```

