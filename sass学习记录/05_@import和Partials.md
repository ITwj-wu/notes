## `@improt`

- @import指令让我们导入其他文件等内容

```css
@import "fileName"
```

### 注意：

- 包含文件时不需要指定文件后缀，Sass会自动添加后缀`.scss`
- 也可以导入`CSS`文件

## `Sass Partials`

- 如果你不希望将一个 Sass 的代码文件编译到一个 CSS 文件，你可以在文件名的**开头添加一个下划线**。这将告诉 Sass 不要将其编译到 CSS 文件。
- 但是，在导入语句中我们不需要添加下划线。

```css
/*以下实例创建一个_color.sacss的文件，但不会编译成_colors.css*/
/* _colors.scss 文件代码：*/
$myPink: #EE82EE;
$myBlue: #4169E1;
$myGreen: #8FBC8F;
```

```css
/*导入文件时，则不需要使用下划线*/
@import "colors"
body {
  font-family: Helvetica, sans-serif;
  font-size: 18px;
  color: $myBlue;
}
```

### 注意：

请不要将带下划线与不带下划线的同名文件放置在同一个目录下，比如，`_colors.scss` 和 `colors.scss `不能同时存在于同一个目录下，否则带下划线的文件将会被忽略。