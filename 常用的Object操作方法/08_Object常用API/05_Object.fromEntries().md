## Object.fromEntries()

- `Object.fromEntries()`方法把一个键值对流标转换为一个对象
- 与`Object.entries()`相反，相当于反转了Object.entries()方法返回的数据结构

```js
// 1. 将Map转换为Object
const map = new Map([['foo','bar'],['baz',42]])
const obj = Object.fromEntries(map)
console.log(obj) // { foo: 'bar', baz: 42 }

// 2. 将Array转换为Object
const arr = [ ['0', 'a'], ['1', 'b'], ['2', 'c'] ]
const obj = Object.fromEntries(arr)
console.log(obj)
// { 0: "a", 1: "b", 2: "c" }
```

- 数组处理函数可以这样转换

```js
const object1 = { a: 1, b: 2, c: 3 }

const object2 = Object.fromEntries(
	object.entries(object1).map([key,val])=>[key, val*2]
)
console.log(object2) // { a: 2, b: 4, c: 6}
```

