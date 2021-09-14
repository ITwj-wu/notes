## `Object.getOwnPropertyNames()`

- **`Object.getOwnPropertyNames()`** 返回一个数组，该数组对元素是 `obj`自身拥有的枚举或不可枚举属性名称字符串
- 数组中枚举属性的顺序与通过`for...in`循环`Object.keys`迭代该对象属性时一致。
- 数组中不可枚举属性的顺序未定义

```js
const arr = ["a", "b", "c"];
console.log(Object.getOwnPropertyNames(arr).sort()) // ["0", "1", "2", "length"]

// 类数组对象
const obj = { 0: "a", 1: "b", 2: "c"};
console.log(Object.getOwnPropertyNames(obj).sort()) // ["0", "1", "2"]

// 使用Array.forEach输出属性名和属性值
Object.getOwnPropertyNames(obj).forEach(function(val, idx, array) {
  console.log(val + " -> " + obj[val]);
})
// 0 -> a
// 1 -> b
// 2 -> c

// 不可枚举属性
const my_obj = Object.create({}, {
  getFoo: {
    value: function() { return this.foo; },
    enumerable: false
  }
});
my_obj.foo = 1;

console.log(Object.getOwnPropertyNames(my_obj).sort())
// ["foo", "getFoo"]
```

### 补充

- `Object.getOwnPropertyNames`和`Object.keys`的区别:
- `Object.keys`只适用于可枚举的属性
- `Object.getOwnPropertyNames`返回对象的全部属性名称（包括不可枚举的）

```js
'use strict'
(function () {
    // 人类的构造函数
    const person = function (name, age, sex) {
        this.name = name
        this.age = age
        this.sex = sex
        this.sing = () => {
            console.log('sing');
        }
    }

    // new 一个ladygaga
    const gaga = new person('ladygaga', 26, 'girl')
    
    // 给嘎嘎发放一个不可枚举的身份证
    Object.defineProperty(gaga, 'id', {
        value: '1234567890',
        enumerable: false
    })

    //查看gaga的个人信息
    const arr = Object.getOwnPropertyNames(gaga)
    console.log(arr) // name, age, sex, sing, id
    
    // 注意和getOwnPropertyNames的区别，不可枚举的id没有输出
    const arr1 = Object.keys(gaga)
    console.log(arr1) // name, age, sex, sing
})()
```

1. ### 获取可枚举的属性

   - 可以使用`Object.keys()`
   - `for...in`获取到原型链上的可枚举属性，可以使用`Object.hasOwnProperty()`方法过滤掉

2. ### 获取不可枚举属性

   - 可以使用`Array.prototype.filter()`方法从`getOwnPropertyNames()`方法获取的所有的属性名数组中将可枚举的属性（使用`Object.keys()`方法获得），剩余的属性便是不可枚举的属性了

```js
const target = myObject;
const enum_and_nonenum = Object.getOwnPropertyNames(target);
const enum_only = Object.keys(target);
const nonenum_only = enum_and_nonenum.filter(function(key) {
    const indexInEnum = enum_only.indexOf(key);
    if (indexInEnum == -1) {
        // 没有发现在enum_only健集中意味着这个健是不可枚举的,
        // 因此返回true 以便让它保持在过滤结果中
        return true;
    } else {
        return false;
    }
});

console.log(nonenum_only);
```

### 注意

- 在ES5中，如果参数不是一个原始对象类型，将抛出一个`TypeError`异常
- 在ES2015中，非对象参数将会强制转换为对象

```js
Object.getOwnPropertyNames('foo') // TypeError: "foo" is not an object     (ES5 code)

Object.getOwnPropertyNames('foo') // ['length', '0', '1', '2']             (ES2015 code)
```

