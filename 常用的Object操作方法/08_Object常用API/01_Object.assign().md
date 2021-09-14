## `Object.assign()`

- 用于将所有可枚举属性的值从一个或多个源对象分配到目标对象
- 将返回目标对象
- 常用来合并对象

```js
const obj1 = { a: 1, b: 2 }
const obj2 = { b: 4, c: 5 }

const obj3 = Object.assign(obj1, obj2)
const obj4 = Object.assign({}, obj1) // 克隆了obj1对象

console.log(obj1) // { a: 1, b: 4, c: 5 }
console.log(obj2) // { b: 4, c: 5 }
console.log(obj3) // { a: 1, b: 4, c: 5 }
console.log(obj4) // { a: 1, b: 4, c: 5 }
```

**语法**

```js
Object.assign(target, ...sources)
```

- 参数：`target`目标参数，`sources`源对象
- 返回值：目标对象

**注意**

- 如果目标对象的属性具有相同的键，则属性将被源对象中的属性覆盖
- `Object.assign` 方法只会拷贝源对象自身并且可枚举的属性到目标对象
- assign其实是浅拷贝而不是深拷贝
- `Object.assign`不会在那些`source`对象值为`null`或`undefined`的时候抛出错误