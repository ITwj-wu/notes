## `BigInt`

`BigInt`是ES10新加的一种JavaScript数据类型，用来表示大于`2^53-1`的整数，`2^53 - 1`是ES10之前，JavaScript所能表示最大的数字

```js
const bigNum = BigInt(17388493920332)
console.log(typeof bigNum) // bigint
```

**所以现在有八种数据类型：**

- Number
- String
- boolean
- undefined
- null
- Object         引用数据类型
- Symbol
- BigInt

**Object包含哪几种类型**

- Array
- function
- Data

**`null`和`undefined`的区别**

- `null`只有一个值，是null，表示一个空指针对象
- undefined只是一个值，是undefined，没有初始化，undefined是从null中派生出来的
- 简单理解就是：undefined是没有定义的，null是定义了但是为空

