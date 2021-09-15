## `String.trimStart`和`String.trimEnd`

`JavaScript`有个`trim`方法，可以清除字符串首尾的空格

```js
const str = "   wjj   "
console.log(str.trim()) // "wjj"
```

`String.trimStart`和`String.trimEnd`分别是去除首尾空格的方法

```js
const str = "   wjj   "
console.log(str.trimStart()) // "wjj   "
console.log(str.trimEnd()) // "   wjj"
```

