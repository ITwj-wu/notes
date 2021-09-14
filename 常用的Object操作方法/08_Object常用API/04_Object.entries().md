## `Object.entries()`

- `Object.entries()`方法返回一个给定对象自身可枚举属性的**键值对数组**
- 可使用`Object.fromEntries()`方法，相当于反转了`Object.entries()`方法返回的数据结构

```js
const obj1 = {
    name: 'wjj',
    age: 20
}
for (const [key, val] of Object.entries(obj1)){
    console.log(`${key}: ${val}`)
}
// "name: wjj"
// "age: 20"

const obj2 = { foo: 'bar', baz: 42 }
console.log(Object.entries(obj2)) // [['foo', 'bar'],['baz',42]]

const obj3 = { 0: 'a', 1: 'b', 2: 'c' }
console.log(Object.entries(obj3)) // [['0','a'],['1','b'],['2','c']]
```

### 补充：

- 将`Object`转换为`Map`,`new Map()`构造函数接受一个可迭代的`entries`
- 借助`Object.entries`方法可以很容易将`Object`转换为`Map`

```js
const obj = {foo: 'bar', baz: 42 }
const map = new Map(Object.entries(obj))
console.log(map) // Map { foo: "bar", baz: 42 }
```

