## `Set`和`Map`

**Set**

1. 基本用法

```js
// add添加元素
const set1 = new Set()
set1.add(1)
set1.add(2)
console.log(set1) // Set(2) { 1, 2 }

// 可传数组
const set2 = new Set([1, 2, 3])
console.log(set2) // Set(3) { 1, 2, 3 }

//是否含有某个元素，使用has
console.log(set2.has(2)) // true
//查看长度 使用size
console.log(set2.size) // 3
// 删除元素 使用delete
set2.delete(2)
console.log(set2) // Set(2) { 1, 3 }
```

        2. 不重复性

```js
// 增加一个已有元素，则增加无效，会被自动去重

//传入的数组有重复项，会被自动去重
const set2 = nwe Set([1, 2, 'wjj', 3, 3, 'wjj'])
console.log(set2) // Set(4) { 1, 2, 'wjj', 3 }
```

Set的不重复性中，要注意**引用类型**和**NaN**

```js
// 两个对象是不同的指针，所以没法去重
const set1 = new Set([1, { name: 'wjj' }, 2, { name: 'wjj' }])
console.log(set1) // Set(4){ 1, { name: 'wjj' }, 2, { name: 'wjj' } }

// 如果两个对象是同一指针，则能去重
const obj = { name: 'wjj' }
const set2 = new Set([1, obj, 2, obj])
console.log(set2) // Set(3) { 1, {name: 'wjj'}, 2 }

//咱们都知道 NaN !== NaN ,NaN是自身不等于自身的,但在Set中还是会被去重
const set = new Set([1, NaN, 1, NaN])
console.log(set) // Set(2) { 1, NaN }
```

利用`Set`的不重复性，可以实现数组去重

```js
const arr = [1, 2, 3, 4, 4, 5, 6, 6, 7, 1]

// Set可利用扩展运算符转为数组
const quchongArr = [...new Set(arr)]
console.log(quchongArr) // [1, 2, 3, 4, 5, 6, 7]

```

**Map**

`Map`对比`Object`的最大好处就是，`key`不受类型限制

```js
// 定义map
const map1 = new Map()
// 新增键值对 使用set(key,value)
map1.set(true, 1)
map1.set(1,2)
map1.set('哈啊哈','嘻嘻嘻')
console.log(map1) // Map(3) { true=>1, 1=>2, '哈啊哈'=>'嘻嘻嘻' }

//判断map中是否含有某个key，使用has(key)
console.log(map1.has('哈啊哈')) // true

//获取某个key对应的value使用get(key)
console.log(map1.get(true)) // 1

//删除map中某个键值对，使用delete(key)
map.delete('哈啊哈')
console.log(map1) // { true=>1, 1=>2 }

//定义map，可传键值对数组集合
const map2 = new Map([[true, 1], [1, 2], ['哈啊哈', '嘻嘻嘻']])
console.log(map2) // Map(3) { true=>1, 1=>2, '哈啊哈'=>'嘻嘻嘻' }
```





