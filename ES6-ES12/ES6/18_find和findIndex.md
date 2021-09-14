`find`和`findIndex`

- `find`: 找到返回被找元素，找不到返回undefined
- `findIndex`: 找到返回被找元素索引，找不到返回-1

```js
const findArr = [
    { name: '科比', no: '24' },
    { name: '罗斯', no: '1' },
    { name: '利拉德', no: '0' }
]

const kobe = findArr.find(({name}) => name === '科比')
const kobeIndex = findArr.findIndex(({name}) => name === '科比') 
console.log(kobe) // { name:'科比', no:'24' }
console.log(kobeIndex) // 0
```

