## display的值
- block
- inline
- inline-block:实现与clear同样的效果

  你可以使用 inline-block 来布局。有一些事情需要你牢记：
vertical-align 属性会影响到 inline-block 元素，你可能会把它的值设置为 top 。
你需要设置每一列的宽度
如果HTML源代码中元素之间有空格，那么列与列之间会产生空隙。

- none
- list-item
- table
- flex:见本文末尾

## margin:0 auto;
> `.main {
  width: 600px;
  margin: 0 auto; 
}`

> `<div class="main">`

设置块级元素的 width 可以阻止它从左到右撑满容器。然后你就可以设置左右外边距为 auto 来使其水平居中。元素会占据你所指定的宽度，然后剩余的宽度会一分为二成为左右外边距。

唯一的问题是，当浏览器窗口比元素的宽度还要窄时，浏览器会显示一个水平滚动条来容纳页面。让我们再来改进下这个方案...

在这种情况下使用 max-width 替代 width 可以使浏览器更好地处理小窗口的情况。这点在移动设备上显得尤为重要，调整下浏览器窗口大小检查下吧！

## box-sizing

当你设置一个元素为 box-sizing: border-box; 时，此元素的内边距和边框不再会增加它的宽度。

## position的值
- static:static 是默认值。任意 `position: static;` 的元素不会被特殊的定位。

- relative:在一个相对定位（position属性的值为relative）的元素上设置 top 、 right 、 bottom 和 left 属性会使其偏离其正常位置。其他的元素则不会调整位置来弥补它偏离后剩下的空隙。

- fixed:一个固定定位（position属性的值为fixed）元素会相对于视窗来定位，这意味着即便页面滚动，它还是会停留在相同的位置。和 relative 一样， top 、 right 、 bottom 和 left 属性都可用。一个固定定位元素不会保留它原本在页面应有的空隙。

- absolute:absolute 是最棘手的position值。 absolute 与 fixed 的表现类似，除了它不是相对于视窗而是相对于最近的“positioned”祖先元素。如果绝对定位（position属性的值为absolute）的元素没有“positioned”祖先元素，那么它是相对于文档的 body 元素，并且它会随着页面滚动而移动。记住一个“positioned”元素是指p osition 值不是 static 的元素。

## float
Float 可用于实现文字环绕图片

清楚浮动：使用 `clear:left;`或者`clear:right;`
    或者`.clearfix {overflow: auto;zoom: 1;}`

## 媒体查询
“响应式设计（Responsive Design）”是一种让网站针对不同的浏览器和设备“响应”不同显示效果的策略，这样可以让网站在任何情况下显示的很棒！

媒体查询是做此事所需的最强大的工具。让我们使用百分比宽度来布局，然后在浏览器变窄到无法容纳侧边栏中的菜单时，把布局显示成一列：
`@media screen and (min-width:600px) {
  nav {
    float: left;
    width: 25%;
  }
  section {
    margin-left: 25%;
  }
}
@media screen and (max-width:599px) {
  nav li {
    display: inline;
  }
}`
## column

新的CSS属性，可以帮助你很轻松的实现文字的多列布局。

`.three-column {
  padding: 1em;
  -moz-column-count: 3;
  -moz-column-gap: 1em;
  -webkit-column-count: 3;
  -webkit-column-gap: 1em;
  column-count: 3;
  column-gap: 1em;
}`

## 使用flexbox 布局

这些例子目前只能在支持 flexbox 的 Chrome 浏览器中运行，基于最新的标准。

 - 使用 Flexbox 的简单布局
 `.container {
  display: -webkit-flex;
  display: flex;
}
nav {
  width: 200px;
}
.flex-column {
  -webkit-flex: 1;
          flex: 1;
}`
- 使用 Flexbox 的牛逼布局
`.container {
  display: -webkit-flex;
  display: flex;
}
.initial {
  -webkit-flex: initial;
          flex: initial;
  width: 200px;
  min-width: 100px;
}
.none {
  -webkit-flex: none;
          flex: none;
  width: 200px;
}
.flex1 {
  -webkit-flex: 1;
          flex: 1;
}
.flex2 {
  -webkit-flex: 2;
          flex: 2;
}`
- 使用flexbox的居中布局
`.vertical-container {
  height: 300px;
  display: -webkit-flex;
  display:         flex;
  -webkit-align-items: center;
          align-items: center;
  -webkit-justify-content: center;
          justify-content: center;
}`
