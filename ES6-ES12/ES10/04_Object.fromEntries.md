## `Object.fromEntries`

前面的ES8的`Object.entries`是把对象转成键值对数组，而`Object.fromEntries`则相反，是**把键值对数组转为对象**

```js
const arr = [
    ['name', 'wjj'],
    ['age', 20],
    ['gender', '女']
]
console.log(Object.formEntries(arr))
// { name: 'wjj', age: 20, gender: '女'}
```

**将Map转为对象**

```js
const map = new Map()
map.set('name', 'wjj')
map.set('age', 20)
map.set('gender', '女')

console.log(map) // Map(3) {'name'=>'wjj', 'age'=>20, 'gender'=> '女'}

const obj = Object.fromEntries(map)
console.log(obj) // { name: 'wjj', age: 20, gender: '女'}
```

