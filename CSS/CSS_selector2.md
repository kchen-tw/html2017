#CSS 选择器
##CSS 后代选择器
**后代选择器（descendant selector）又称为包含选择器。**
**后代选择器可以选择作为某元素后代的元素。**

###根据上下文选择元素
我们可以定义后代选择器来创建一些规则，使这些规则在某些文档结构中起作用，而在另外一些结构中不起作用。
举例来说，如果您希望只对 h1 元素中的 em 元素应用样式，可以这样写：

```css
h1 em {color:red;}
```

上面这个规则会把作为 h1 元素后代的 em 元素的文本变为 红色。其他 em 文本（如段落或块引用中的 em）则不会被这个规则选中：

```html
<h1>This is a <em>important</em> heading</h1>
<p>This is a <em>important</em> paragraph.</p>
```

当然，您也可以在 h1 中找到的每个 em 元素上放一个 class 属性，但是显然，后代选择器的效率更高。

###语法解释
在后代选择器中，规则左边的选择器一端包括两个或多个用空格分隔的选择器。选择器之间的空格是一种结合符（combinator）。每个空格结合符可以解释为“... 在 ... 找到”、“... 作为 ... 的一部分”、“... 作为 ... 的后代”，但是要求必须从右向左读选择器。

因此，h1 em 选择器可以解释为 “作为 h1 元素后代的任何 em 元素”。如果要从左向右读选择器，可以换成以下说法：“包含 em 的所有 h1 会把以下样式应用到该 em”。

###具体应用
后代选择器的功能极其强大。有了它，可以使 HTML 中不可能实现的任务成为可能。

假设有一个文档，其中有一个边栏，还有一个主区。边栏的背景为蓝色，主区的背景为白色，这两个区都包含链接列表。不能把所有链接都设置为蓝色，因为这样一来边栏中的蓝色链接都无法看到。

解决方法是使用后代选择器。在这种情况下，可以为包含边栏的 div 指定值为 sidebar 的 class 属性，并把主区的 class 属性值设置为 maincontent。然后编写以下样式：

```css
div.sidebar {background:blue;}
div.maincontent {background:white;}
div.sidebar a:link {color:white;}
div.maincontent a:link {color:blue;}
```

有关后代选择器有一个易被忽视的方面，即两个元素之间的层次间隔可以是无限的。
例如，如果写作 ul em，这个语法就会选择从 ul 元素继承的所有 em 元素，而不论 em 的嵌套层次多深。

因此，ul em 将会选择以下标记中的所有 em 元素：

```html
<ul>
  <li>List item 1
    <ol>
      <li>List item 1-1</li>
      <li>List item 1-2</li>
      <li>List item 1-3
        <ol>
          <li>List item 1-3-1</li>
          <li>List item <em>1-3-2</em></li>
          <li>List item 1-3-3</li>
        </ol>
      </li>
      <li>List item 1-4</li>
    </ol>
  </li>
  <li>List item 2</li>
  <li>List item 3</li>
</ul>
```

___

##CSS 子元素选择器
**与后代选择器相比，子元素选择器（Child selectors）只能选择作为某元素子元素的元素。**
###选择子元素
如果您不希望选择任意的后代元素，而是希望缩小范围，只选择某个元素的子元素，请使用子元素选择器（Child selector）。
例如，如果您希望选择只作为 h1 元素子元素的 strong 元素，可以这样写：

```css
h1 > strong {color:red;}
```

这个规则会把第一个 h1 下面的两个 strong 元素变为红色，但是第二个 h1 中的 strong 不受影响：

```html
<h1>This is <strong>very</strong> <strong>very</strong> important.</h1>
<h1>This is <em>really <strong>very</strong></em> important.</h1>
```

###语法解释
您应该已经注意到了，子选择器使用了大于号（子结合符）。
子结合符两边可以有空白符，这是可选的。因此，以下写法都没有问题：

```css
h1 > strong
h1> strong
h1 >strong
h1>strong
```

如果从右向左读，选择器 h1 > strong 可以解释为“选择作为 h1 元素子元素的所有 strong 元素”。

###结合后代选择器和子选择器
请看下面这个选择器：

```css
table.company td > p
```

上面的选择器会选择作为 td 元素子元素的所有 p 元素，这个 td 元素本身从 table 元素继承，该 table 元素有一个包含 company 的 class 属性。

___

##CSS 相邻兄弟选择器
**相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。**
###选择相邻兄弟
如果需要选择紧接在另一个元素后的元素，而且二者有相同的父元素，可以使用相邻兄弟选择器（Adjacent sibling selector）。
例如，如果要增加紧接在 h1 元素后出现的段落的上边距，可以这样写：

```css
h1 + p {margin-top:50px;}
```

这个选择器读作：“选择紧接在 h1 元素后出现的段落，h1 和 p 元素拥有共同的父元素”。

###语法解释
相邻兄弟选择器使用了加号（+），即相邻兄弟结合符（Adjacent sibling combinator）。
注释：与子结合符一样，相邻兄弟结合符旁边可以有空白符。
请看下面这个文档树片段：

```html
<div>
  <ul>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ul>
  <ol>
    <li>List item 1</li>
    <li>List item 2</li>
    <li>List item 3</li>
  </ol>
</div>
```

在上面的片段中，div 元素中包含两个列表：一个无序列表，一个有序列表，每个列表都包含三个列表项。这两个列表是相邻兄弟，列表项本身也是相邻兄弟。不过，第一个列表中的列表项与第二个列表中的列表项不是相邻兄弟，因为这两组列表项不属于同一父元素（最多只能算堂兄弟）。
请记住，用一个结合符只能选择两个相邻兄弟中的第二个元素。请看下面的选择器：

```css
li + li {font-weight:bold;}
```

上面这个选择器只会把列表中的第二个和第三个列表项变为粗体。第一个列表项不受影响。

####结合其他选择器
相邻兄弟结合符还可以结合其他结合符：

```css
html > body table + ul {margin-top:20px;}
```

这个选择器解释为：选择紧接在 table 元素后出现的所有兄弟 ul 元素，该 table 元素包含在一个 body 元素中，body 元素本身是 html 元素的子元素。

___

##CSS 伪类 (Pseudo-classes)
**CSS 伪类用于向某些选择器添加特殊的效果。**

###语法
伪类的语法：

```css
selector : pseudo-class {property: value}
```

CSS 类也可与伪类搭配使用。

```css
selector.class : pseudo-class {property: value}
```

###锚伪类
在支持 CSS 的浏览器中，链接的不同状态都可以不同的方式显示，这些状态包括：活动状态，已被访问状态，未被访问状态，和鼠标悬停状态。

```css
a:link {color: #FF0000}		/* 未访问的链接 */
a:visited {color: #00FF00}	/* 已访问的链接 */
a:hover {color: #FF00FF}	/* 鼠标移动到链接上 */
a:active {color: #0000FF}	/* 选定的链接 */
```

提示：在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
提示：在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
提示：伪类名称对大小写不敏感。

###伪类与 CSS 类
伪类可以与 CSS 类配合使用：

```html
a.red : visited {color: #FF0000}

<a class="red" href="css_syntax.asp">CSS Syntax</a>
```

假如上面的例子中的链接被访问过，那么它将显示为红色。

###CSS2 - :first-child 伪类
您可以使用 :first-child 伪类来选择元素的第一个子元素。这个特定伪类很容易遭到误解，所以有必要举例来说明。考虑以下标记：

```html
<div>
<p>These are the necessary steps:</p>
<ul>
<li>Intert Key</li>
<li>Turn key <strong>clockwise</strong></li>
<li>Push accelerator</li>
</ul>
<p>Do <em>not</em> push the brake at the same time as the accelerator.</p>
</div>
```

在上面的例子中，作为第一个元素的元素包括第一个 p、第一个 li 和 strong 和 em 元素。
给定以下规则：

```css
p:first-child {font-weight: bold;}
li:first-child {text-transform:uppercase;}
```

第一个规则将作为某元素第一个子元素的所有 p 元素设置为粗体。第二个规则将作为某个元素（在 HTML 中，这肯定是 ol 或 ul 元素）第一个子元素的所有 li 元素变成大写。

提示：最常见的错误是认为 p:first-child 之类的选择器会选择 p 元素的第一个子元素。

注释：必须声明 `<!DOCTYPE>`，这样 :first-child 才能在 IE 中生效。
为了使您更透彻地理解 :first-child 伪类，我们另外提供了 3 个例子：

例子 1 - 匹配第一个 `<p>` 元素
在下面的例子中，选择器匹配作为任何元素的第一个子元素的 p 元素：

```html
<html>
<head>
<style type="text/css">
p:first-child {
  color: red;
  } 
</style>
</head>

<body>
<p>some text</p>
<p>some text</p>
</body>
</html>
```

例子 2 - 匹配所有 `<p>` 元素中的第一个 `<i>` 元素
在下面的例子中，选择器匹配所有 `<p>` 元素中的第一个 `<i>` 元素：

```html
<html>
<head>
<style type="text/css">
p > i:first-child {
  font-weight:bold;
  } 
</style>
</head>

<body>
<p>some <i>text</i>. some <i>text</i>.</p>
<p>some <i>text</i>. some <i>text</i>.</p>
</body>
</html>
```

例子 3 - 匹配所有作为第一个子元素的 `<p>` 元素中的所有 `<i>` 元素
在下面的例子中，选择器匹配所有作为元素的第一个子元素的 `<p>` 元素中的所有 `<i>` 元素：

```html
<html>
<head>
<style type="text/css">
p:first-child i {
  color:blue;
  } 
</style>
</head>

<body>
<p>some <i>text</i>. some <i>text</i>.</p>
<p>some <i>text</i>. some <i>text</i>.</p>
</body>
</html>
```

###CSS2 - :lang 伪类
:lang 伪类使你有能力为不同的语言定义特殊的规则。在下面的例子中，:lang 类为属性值为 no 的 q 元素定义引号的类型：

```html
<html>
<head>

<style type="text/css">
q:lang(no)
   {
   quotes: "~" "~"
   }
</style>

</head>

<body>
<p>文字<q lang="no">段落中的引用的文字</q>文字</p>
</body></html>
```

###伪类
**W3C**："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。

属性|	描述|	CSS
:--:|:--:|:--:
:active	|向被激活的元素添加样式。	|1
:focus|	向拥有键盘输入焦点的元素添加样式。|	2
:hover|	当鼠标悬浮在元素上方时，向元素添加样式。	|1
:link|	向未被访问的链接添加样式。	|1
:visited|	向已被访问的链接添加样式。	|1
:first-child|	向元素的第一个子元素添加样式。	|2
:lang|	向带有指定 lang 属性的元素添加样式。	|2

___

##CSS 伪元素 (Pseudo-elements)
**CSS 伪元素用于向某些选择器设置特殊效果。**

###语法
伪元素的语法：

```css
selector:pseudo-element {property:value;}
```
CSS 类也可以与伪元素配合使用：

```css
selector.class:pseudo-element {property:value;}
```

##:first-line 伪元素
"first-line" 伪元素用于向文本的首行设置特殊样式。
在下面的例子中，浏览器会根据 "first-line" 伪元素中的样式对 p 元素的第一行文本进行格式化：

实例

```css
p:first-line
  {
  color:#ff0000;
  font-variant:small-caps;
  }
```

注释："first-line" 伪元素只能用于块级元素。
注释：下面的属性可应用于 "first-line" 伪元素：

* font
* color
* background
* word-spacing
* letter-spacing
* text-decoration
* vertical-align
* text-transform
* line-height
* clear

###:first-letter 伪元素
"first-letter" 伪元素用于向文本的首字母设置特殊样式：

```css
p:first-letter
  {
  color:#ff0000;
  font-size:xx-large;
  }
```

注释："first-letter" 伪元素只能用于块级元素。
注释：下面的属性可应用于 "first-letter" 伪元素：

* font
* color
* background
* margin
* padding
* border
* text-decoration
* vertical-align(仅当 float 为 none 时)
* text-transform
* line-height
* float
* clear

###伪元素和 CSS 类
伪元素可以与 CSS 类配合使用：

```html
p.article:first-letter
  {
  color: #FF0000;
  }

<p class="article">This is a paragraph in an article。</p>
```
上面的例子会使所有 class 为 article 的段落的首字母变为红色。

###多重伪元素
可以结合多个伪元素来使用。

在下面的例子中，段落的第一个字母将显示为红色，其字体大小为 xx-large。第一行中的其余文本将为蓝色，并以小型大写字母显示。段落中的其余文本将以默认字体大小和颜色来显示：

```css
p:first-letter
  {
  color:#ff0000;
  font-size:xx-large;
  }

p:first-line
  {
  color:#0000ff;
  font-variant:small-caps;
  }
```

###CSS2 - :before 伪元素
":before" 伪元素可以在元素的内容前面插入新内容。
下面的例子在每个 `<h1>` 元素前面插入一幅图片：

```css
h1:before
  {
  content:url(logo.gif);
  }
```

###CSS2 - :after 伪元素
":after" 伪元素可以在元素的内容之后插入新内容。
下面的例子在每个 `<h1>` 元素后面插入一幅图片：

```css
h1:after
  {
  content:url(logo.gif);
  }
```

###伪元素
**W3C**："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。

属性|	描述|	CSS
:--:|:--:|:--:
:first-letter|	向文本的第一个字母添加特殊样式。	|1
:first-line|	向文本的首行添加特殊样式。	|1
:before|	在元素之前添加内容。	|2
:after|	在元素之后添加内容。	|2