## `includes`

传入元素，如果数组中能找到此元素，则返回true,否则返回false

```js
const includeArr = [1, 2 , 3, '林三心', '科比']

const isKobe = includeArr.includes('科比')
console.log(isKobe) // true
```

跟`indexOf`很像，但还是有区别的

```js
const arr = [1, 2, NaN]

console.log(arr.indexOf(NaN)) // -1  indexOf找不到NaN
console.log(arr.includes(NaN)) // true includes能找到NaN
```

