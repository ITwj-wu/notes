## `Object.values()`

- `Object.values()`方法返回一个给定对象自身的所有可枚举属性值的数组
- 值的顺序与使用`for...in`循环顺序相同（区别在于for-in循环枚举原型链中的属性）

```js
const obj1 = { foo: 'bar', baz: 42 }
console.log(Object.values(obj1)) // ['bar', 42]

const obj2 = { 0: 'a', 1: 'b', 2: 'c' }
console.log(Object.values(obj2)) // ['a', 'b', 'c']
```

### 注意

对象`key`为`number`的话，会从升序枚举返回

```js
const obj3 = { 100: 'a', 2: 'b', 7: 'c' }
console.log(Object.keys(obj3)) // ['b', 'c', 'a' ]
```

