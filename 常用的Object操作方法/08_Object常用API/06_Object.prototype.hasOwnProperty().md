## `Object.prototype.hasOwnProperty()`

- 枚举对象为了避免`for...in`遍历继承来的属性，可以借助`Object.prototype.hasOwnProperty()`方法来判断
- `hasOwnProperty()`方法会返回一个布尔值，判断对象自身属性是否具有指定属性

```js
const obj1 = {}
obj1.property1 = 10

console.log(obj1.hasOwnProperty('property1')) // true
console.log(obj1.hasOwnproperty('hasOwnProperty')) // false
console.log(obj1.hasOwnproperty('toString')) // false
```

### 注意：

- 只会对自身属性进行判断，继承来的一律返回false
- 配合`for...in`使用，可以避免遍历继承来的属性
- 即使属性是值是`null`或`undefined`,只要属性存在，`hasOwnProperty`依旧会返回`true`

```js
const o = new Object();
o.propOne = null
o.propTwo = undefined

console.log(o.hasOwnProperty('propOne')) // true
console.log(o.hasOwnProperty('propTwo')) // true
```

