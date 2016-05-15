## 伪类选择器
CSS伪类（pseudo-class）是加在选择器后面的用来指定元素状态的关键字。比如，:hover 会在鼠标悬停在选中元素上时应用相应的样式。

伪类和伪元素（pseudo-elements）不仅可以让你为符合某种文档树结构的元素指定样式，还可以为符合某些外部条件的元素指定样式：浏览历史(比如是否访问过 (:visited)， 内容状态(如 :checked ), 鼠标位置 (如:hover). 完整列表参见 CSS3 Selectors working spec.

伪类列表

参考网址： [https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Getting_Started/Selectors](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Getting_Started/Selectors)

- :link
- :visited
- :active
- :hover
- :focus
- :first-child
- :nth-child
- :nth-last-child
- :nth-of-type
- :first-of-type
- :last-of-type
- :empty
- :target
- :checked
- :enabled
- :disabled

## 基于关系的选择器

选择器 |选择的元素
------|------
A E   |任何是元素A的后代元素E (后代节点指A的子节点，子节点的子节点，以此类推)
A > E |任何元素A的子元素
E:first-child|任何元素的第一个子元素E
B + E|任何元素B的下一个兄弟元素E
B ~ E|B元素后面的拥有共同父元素的兄弟元素E

