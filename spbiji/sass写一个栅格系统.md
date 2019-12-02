# sass写一个栅格系统



sass网站：https://www.sass.hk/



1.sass可以定义变量，具有运算符，简单的逻辑判断的css扩展语言。

# 1-1. 变量声明

`sass`变量的声明和`css`属性的声明很像：

这意味着变量`$highlight-color`现在的值是`#F90`。任何可以用作`css`属性值的赋值都 可以用作`sass`的变量值，甚至是以空格分割的多个属性值，如`$basic-border: 1px solid black;`，或以逗号分割的多个属性值，如`$plain-font: "Myriad Pro"、Myriad、"Helvetica Neue"、Helvetica、"Liberation Sans"、Arial和sans-serif; sans-serif;`。这时变 量还没有生效，除非你引用这个变量——我们很快就会了解如何引用。

# 1-2. 变量引用

凡是`css`属性的标准值（比如说1px或者bold）可存在的地方，变量就可以使用。`css`生成时，变量会被它们的值所替代。之后，如果你需要一个不同的值，只需要改变这个变量的值，则所有引用此变量的地方生成的值都会随之改变。****

```css
$highlight-color: #F90;
.selected {
  border: 1px solid $highlight-color;
}

//编译后

.selected {
  border: 1px solid #F90;
}
```



看上边示例中的`$highlight-color`变量，它被直接赋值给`border`属性，当这段代码被编译输出`css`时，`$highlight-color`会被`#F90`这一颜色值所替代。产生的效果就是给`selected`这个类一条1像素宽、实心且颜色值为`#F90`的边框。



### 2.1. @for

`@for` 指令可以在限制的范围内重复输出格式，每次按要求（变量的值）对输出结果做出变动。这个指令包含两种格式：`@for $var from  through `，或者 `@for $var from  to `，区别在于 `through` 与 `to` 的含义：*当使用 `through` 时，条件范围包含 `` 与 `` 的值，而使用 `to` 时条件范围只包含 `` 的值不包含 `` 的值*。另外，`$var` 可以是任何变量，比如 `$i`；`` 和 `` 必须是整数值。

```scss
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}
```

编译为

```css
.item-1 {
  width: 2em; }
.item-2 {
  width: 4em; }
.item-3 {
  width: 6em; }
```



### 2.2. @each

`@each` 指令的格式是 `$var in `, `$var` 可以是任何变量名，比如 `$length` 或者 `$name`，而 `` 是一连串的值，也就是值列表。

`@each` 将变量 `$var` 作用于值列表中的每一个项目，然后输出结果，例如：

```scss
@each $animal in puma, sea-slug, egret, salamander {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}
```

编译为

```css
.puma-icon {
  background-image: url('/images/puma.png'); }
.sea-slug-icon {
  background-image: url('/images/sea-slug.png'); }
.egret-icon {
  background-image: url('/images/egret.png'); }
.salamander-icon {
  background-image: url('/images/salamander.png'); }
```