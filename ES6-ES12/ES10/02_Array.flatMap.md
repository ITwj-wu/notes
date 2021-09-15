## `Array.flatMap`

需求

```js
let arr = ["小黑 小黄 摩卡", "哈根儿 小白 黑聪" ]

// 将上面数组转为
['小黑','小黄','摩卡','哈根儿','小白','黑聪']
```

想到`map`+`flat`

```js
arr.map((item, index, arr) => item.split(" ").flat())
// ['小黑','小黄','摩卡','哈根儿','小白','黑聪']
```

`flatMap`就是`map`+`flat` 一个顶俩

```js
arr.flatMap(x => x.split(" "))
// ['小黑','小黄','摩卡','哈根儿','小白','黑聪']
```

