## `Object.keys()`

**`Object.keys()`** 方法会返回一个由一个给定对象的自身可枚举属性组成的数组，数组中属性名的排列顺序和正常循环遍历该对象时返回的顺序一致。

```js
const arr = ['a', 'b', 'c']
console.log(Object.keys(arr)) // ['0', '1', '2']

const obj = { 0: 'a', 1: 'b', 2: 'c' }
console.log(Object.keys(obj)) // ['0', '1', '2']

const obj2 = { 100: 'a', 2: 'b', 7: 'c' }
console.log(Object.keys(obj2)) // ['2', '7', '100']
```

### 注意

- 在ES5里，如果此方法的参数不是对象（而是一个原始值），那么它会抛出`TypeError`。
- 在ES2015中，非对象的参数将被强制转换为一个对象

```js
Object.keys("wjj") // TypeError: "foo" is not an object       (ES5 code)

Object.keys("wjj") // ["0", "1", "2"]                         (ES2015 code)
```

