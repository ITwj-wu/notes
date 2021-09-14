## @mixin 和 @include

- @mixin 指令允许我们定义一个可以在整个样式表中重复使用的样式。

- @include 指令可以将混入（mixin）引入到文档中。

```css
@mixin important-text {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
}
```

```css
.danger {
  @include important-text;
  background-color: green;
}
```

## css代码

```css
.danger {
  color: red;
  font-size: 25px;
  font-weight: bold;
  border: 1px solid blue;
  background-color: green;
}
```



