#CSS 选择器
##CSS 元素选择器
最常见的 CSS 选择器是元素选择器。换句话说，文档的元素就是最基本的选择器。
如果设置 HTML 的样式，选择器通常将是某个 HTML 元素，比如 p、h1、em、a，甚至可以是 html 本身：

```css
html {color:black;}
h1 {color:blue;}
h2 {color:silver;}
```

可以将某个样式从一个元素切换到另一个元素。
假设您决定将上面的段落文本（而不是 h1 元素）设置为灰色。只需要把 h1 选择器改为 

```css
p：
html {color:black;}
p {color:gray;}
h2 {color:silver;}
```

###类型选择器
在 W3C 标准中，元素选择器又称为类型选择器（type selector）。
“类型选择器匹配文档语言元素类型的名称。类型选择器匹配文档树中该元素类型的每一个实例。”
下面的规则匹配文档树中所有 h1 元素：

```css
h1 {font-family: sans-serif;}
```

因此，我们也可以为 XML 文档中的元素设置样式：
XML 文档：

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<?xml-stylesheet type="text/css" href="note.css"?>
<note>
<to>George</to>
<from>John</from>
<heading>Reminder</heading>
<body>Don't forget the meeting!</body>
</note>
```

CSS 文档：

```css
note
  {
  font-family:Verdana, Arial;
  margin-left:30px;
  }

to
  {
  font-size:28px;
  display: block;
  }

from
  {
  font-size:28px;
  display: block;
  }

heading
  {
  color: red;
  font-size:60px;
  display: block;
  }

body
  {
  color: blue;
  font-size:35px;
  display: block;
  }
```

___
##CSS 分组
###选择器分组
假设希望 h2 元素和段落都有灰色。为达到这个目的，最容易的做法是使用以下声明：

```css
h2, p {color:gray;}
```

将 h2 和 p 选择器放在规则左边，然后用逗号分隔，就定义了一个规则。其右边的样式（color:gray;）将应用到这两个选择器所引用的元素。逗号告诉浏览器，规则中包含两个不同的选择器。如果没有这个逗号，那么规则的含义将完全不同。参见后代选择器。

可以将任意多个选择器分组在一起，对此没有任何限制。
例如，如果您想把很多元素显示为灰色，可以使用类似如下的规则：

```css
body, h2, p, table, th, td, pre, strong, em {color:gray;}
```

提示：通过分组，创作者可以将某些类型的样式“压缩”在一起，这样就可以得到更简洁的样式表。

以下的两组规则能得到同样的结果，不过可以很清楚地看出哪一个写起来更容易：

```css
/* no grouping */
h1 {color:blue;}
h2 {color:blue;}
h3 {color:blue;}
h4 {color:blue;}
h5 {color:blue;}
h6 {color:blue;}

/* grouping */
h1, h2, h3, h4, h5, h6 {color:blue;}
```

分组提供了一些有意思的选择。例如，下例中的所有规则分组都是等价的，每个组只是展示了对选择器和声明分组的不同方法：

```css
/* group 1 */
h1 {color:silver; background:white;}
h2 {color:silver; background:gray;}
h3 {color:white; background:gray;}
h4 {color:silver; background:white;}
b {color:gray; background:white;}

/* group 2 */
h1, h2, h4 {color:silver;}
h2, h3 {background:gray;}
h1, h4, b {background:white;}
h3 {color:white;}
b {color:gray;}

/* group 3 */
h1, h4 {color:silver; background:white;}
h2 {color:silver;}
h3 {color:white;}
h2, h3 {background:gray;}
b {color:gray; background:white;}
```

请注意，group 3 中使用了“声明分组”。稍后我们会为您介绍“声明分组”。

###通配符选择器
CSS2 引入了一种新的简单选择器 - 通配选择器（universal selector），显示为一个星号（*）。该选择器可以与任何元素匹配，就像是一个通配符。

例如，下面的规则可以使文档中的每个元素都为红色：
```
* {color:red;}
```

这个声明等价于列出了文档中所有元素的一个分组选择器。利用通配选择器，只需敲一次键（仅一个星号）就能使文档中所有元素的 color 属性值指定为 red。

###声明分组
我们既可以对选择器进行分组，也可以对声明分组。

假设您希望所有 h1 元素都有红色背景，并使用 28 像素高的 Verdana 字体显示为蓝色文本，可以写以下样式：

```css
h1 {font: 28px Verdana;}
h1 {color: blue;}
h1 {background: red;}
```

但是上面这种做法的效率并不高。尤其是当我们为一个有多个样式的元素创建这样一个列表时会很麻烦。相反，我们可以将声明分组在一起：

```css
h1 {font: 28px Verdana; color: white; background: black;}
```

这与前面的 3 行样式表的效果完全相同。

注意，对声明分组，一定要在各个声明的最后使用分号，这很重要。浏览器会忽略样式表中的空白符。只要加了分号，就可以毫无顾忌地采用以下格式建立样式：

```css
h1 {
  font: 28px Verdana;
  color: blue;
  background: red;
  }
```

怎么样，上面这种写法的可读性是不是更强。
不过，如果忽略了第二个分号，用户代理就会把这个样式表解释如下：

```css
h1 {
  font: 28px Verdana;
  color: blue background: red;
  }
```

因为 background 对 color 来说不是一个合法值，而且由于只能为 color 指定一个关键字，所以用户代理会完全忽略这个 color 声明（包括 background: black 部分）。这样 h1 标题只会显示为蓝色，而没有红色背景，不过更有可能根本得不到蓝色的 h1。相反，这些标题只会显示为默认颜色（通常是黑色），而且根本没有背景色。font: 28px Verdana 声明仍能正常发挥作用，因为它确实正确地以一个分号结尾。

与选择器分组一样，声明分组也是一种便利的方法，可以缩短样式表，使之更清晰，也更易维护。

提示：在规则的最后一个声明后也加上分号是一个好习惯。在向规则增加另一个声明时，就不必担心忘记再插入一个分号。
结合选择器和声明的分组
我们可以在一个规则中结合选择器分组和声明分组，就可以使用很少的语句定义相对复杂的样式。
下面的规则为所有标题指定了一种复杂的样式：

```css
h1, h2, h3, h4, h5, h6 {
  color:gray;
  background: white;
  padding: 10px;
  border: 1px solid black;
  font-family: Verdana;
  }
```

上面这条规则将所有标题的样式定义为带有白色背景的灰色文本，其内边距是 10 像素，并带有 1 像素的实心边框，文本字体是 Verdana。

___

##CSS 类选择器详解
**类选择器允许以一种独立于文档元素的方式来指定样式。**
###CSS 类选择器
类选择器允许以一种独立于文档元素的方式来指定样式。
该选择器可以单独使用，也可以与其他元素结合使用。

提示：只有适当地标记文档后，才能使用这些选择器，所以使用这两种选择器通常需要先做一些构想和计划。

要应用样式而不考虑具体设计的元素，最常用的方法就是使用类选择器。

####修改 HTML 代码
在使用类选择器之前，需要修改具体的文档标记，以便类选择器正常工作。

为了将类选择器的样式与元素关联，必须将 class 指定为一个适当的值。请看下面的 HTML 代码：

```html
<h1 class="important">
This heading is very important.
</h1>

<p class="important">
This paragraph is very important.
</p>
```

在上面的代码中，两个元素的 class 都指定为 important：第一个标题（ h1 元素），第二个段落（p 元素）。

#####语法
然后我们使用以下语法向这些归类的元素应用样式，即类名前有一个点号（.），然后结合通配选择器：

```css
*.important {color:red;}
```

如果您只想选择所有类名相同的元素，可以在类选择器中忽略通配选择器，这没有任何不好的影响：

```css
.important {color:red;}
```

####结合元素选择器
类选择器可以结合元素选择器来使用。
例如，您可能希望只有段落显示为红色文本：

```css
p.important {color:red;}
```

选择器现在会匹配 class 属性包含 important 的所有 p 元素，但是其他任何类型的元素都不匹配，不论是否有此 class 属性。选择器 p.important 解释为：“其 class 属性值为 important 的所有段落”。 因为 h1 元素不是段落，这个规则的选择器与之不匹配，因此 h1 元素不会变成红色文本。

如果你确实希望为 h1 元素指定不同的样式，可以使用选择器 h1.important：

```css
p.important {color:red;}
h1.important {color:blue;}
```

###CSS 多类选择器
在上一节中，我们处理了 class 值中包含一个词的情况。在 HTML 中，一个 class 值中可能包含一个词列表，各个词之间用空格分隔。例如，如果希望将一个特定的元素同时标记为重要（important）和警告（warning），就可以写作：

```html
<p class="important warning">
This paragraph is a very important warning.
</p>
```

这两个词的顺序无关紧要，写成 warning important 也可以。

我们假设 class 为 important 的所有元素都是粗体，而 class 为 warning 的所有元素为斜体，class 中同时包含 important 和 warning 的所有元素还有一个银色的背景 。就可以写作：

```css
.important {font-weight:bold;}
.warning {font-style:italic;}
.important.warning {background:silver;}
```

通过把两个类选择器链接在一起，仅可以选择同时包含这些类名的元素（类名的顺序不限）。
如果一个多类选择器包含类名列表中没有的一个类名，匹配就会失败。请看下面的规则：

```css
.important.urgent {background:silver;}
```

不出所料，这个选择器将只匹配 class 属性中包含词 important 和 urgent 的 p 元素。因此，如果一个 p 元素的 class 属性中只有词 important 和 warning，将不能匹配。不过，它能匹配以下元素：

```html
<p class="important urgent warning">
This paragraph is a very important and urgent warning.
</p>
```

重要事项：在 IE7 之前的版本中，不同平台的 Internet Explorer 都不能正确地处理多类选择器。

___

##CSS ID 选择器详解
**ID 选择器允许以一种独立于文档元素的方式来指定样式。**
###CSS ID 选择器
在某些方面，ID 选择器类似于类选择器，不过也有一些重要差别。

####语法
首先，ID 选择器前面有一个 # 号 - 也称为棋盘号或井号。
请看下面的规则：

```css
*#intro {font-weight:bold;}
```

与类选择器一样，ID 选择器中可以忽略通配选择器。前面的例子也可以写作：

```css
#intro {font-weight:bold;}
```

这个选择器的效果将是一样的。
第二个区别是 ID 选择器不引用 class 属性的值，毫无疑问，它要引用 id 属性中的值。
以下是一个实际 ID 选择器的例子：

```html
<p id="intro">This is a paragraph of introduction.</p>
```

###类选择器还是 ID 选择器？
在类选择器这一章中我们曾讲解过，可以为任意多个元素指定类。前一章中类名 important 被应用到 p 和 h1 元素，而且它还可以应用到更多元素。

区别 1：只能在文档中使用一次

与类不同，在一个 HTML 文档中，ID 选择器会使用一次，而且仅一次。

区别 2：不能使用 ID 词列表

不同于类选择器，ID 选择器不能结合使用，因为 ID 属性不允许有以空格分隔的词列表。

区别 3：ID 能包含更多含义

类似于类，可以独立于元素来选择 ID。有些情况下，您知道文档中会出现某个特定 ID 值，但是并不知道它会出现在哪个元素上，所以您想声明独立的 ID 选择器。例如，您可能知道在一个给定的文档中会有一个 ID 值为 mostImportant 的元素。您不知道这个最重要的东西是一个段落、一个短语、一个列表项还是一个小节标题。您只知道每个文档都会有这么一个最重要的内容，它可能在任何元素中，而且只能出现一个。在这种情况下，可以编写如下规则：

```css
#mostImportant {color:red; background:yellow;}
```

这个规则会与以下各个元素匹配（这些元素不能在同一个文档中同时出现，因为它们都有相同的 ID 值）：

```html
<h1 id="mostImportant">This is important!</h1>
<em id="mostImportant">This is important!</em>
<ul id="mostImportant">This is important!</ul>
```

###区分大小写
请注意，类选择器和 ID 选择器可能是区分大小写的。这取决于文档的语言。HTML 和 XHTML 将类和 ID 值定义为区分大小写，所以类和 ID 值的大小写必须与文档中的相应值匹配。
因此，对于以下的 CSS 和 HTML，元素不会变成粗体：

```html
#intro {font-weight:bold;}

<p id="Intro">This is a paragraph of introduction.</p>
```

由于字母 i 的大小写不同，所以选择器不会匹配上面的元素。
___

##CSS 属性选择器详解
**CSS 2 引入了属性选择器。**
**属性选择器可以根据元素的属性及属性值来选择元素。**
###简单属性选择
如果希望选择有某个属性的元素，而不论属性值是什么，可以使用简单属性选择器。

例子 1
如果您希望把包含标题（title）的所有元素变为红色，可以写作：

```css
*[title] {color:red;}
```

例子 2
与上面类似，可以只对有 href 属性的锚（a 元素）应用样式：

```css
a[href] {color:red;}
```

例子 3
还可以根据多个属性进行选择，只需将属性选择器链接在一起即可。
例如，为了将同时有 href 和 title 属性的 HTML 超链接的文本设置为红色，可以这样写：

```css
a[href][title] {color:red;}
```

例子 4
可以采用一些创造性的方法使用这个特性。
例如，可以对所有带有 alt 属性的图像应用样式，从而突出显示这些有效的图像：

```css
img[alt] {border: 5px solid red;}
```

提示：上面这个特例更适合用来诊断而不是设计，即用来确定图像是否确实有效。

例子 5：为 XML 文档使用属性选择器

属性选择器在 XML 文档中相当有用，因为 XML 语言主张要针对元素和属性的用途指定元
素名和属性名。

假设我们为描述太阳系行星设计了一个 XML 文档。如果我们想选择有 moons 属性的所有 planet 元素，使之显示为红色，以便能更关注有 moons 的行星，就可以这样写：

```css
planet[moons] {color:red;}
```
这会让以下标记片段中的第二个和第三个元素的文本显示为红色，但第一个元素的文本不是红色：

```html
<planet>Venus</planet>
<planet moons="1">Earth</planet>
<planet moons="2">Mars</planet>
```

###根据具体属性值选择
除了选择拥有某些属性的元素，还可以进一步缩小选择范围，只选择有特定属性值的元素。

例子 1
例如，假设希望将指向 Web 服务器上某个指定文档的超链接变成红色，可以这样写：

```css
a[href="http://www.w3school.com.cn/about_us.asp"] {color: red;}
```

例子 2
与简单属性选择器类似，可以把多个属性-值选择器链接在一起来选择一个文档。

```css
a[href="http://www.w3school.com.cn/"][title="W3School"] {color: red;}
```

这会把以下标记中的第一个超链接的文本变为红色，但是第二个或第三个链接不受影响：

```html
<a href="http://www.w3school.com.cn/" title="W3School">W3School</a>
<a href="http://www.w3school.com.cn/css/" title="CSS">CSS</a>
<a href="http://www.w3school.com.cn/html/" title="HTML">HTML</a>
```

例子 3
同样地，XML 语言也可以利用这种方法来设置样式。
下面我们再回到行星那个例子中。假设只希望选择 moons 属性值为 1 的那些 planet 元素：

```css
planet[moons="1"] {color: red;}
```

上面的代码会把以下标记中的第二个元素变成红色，但第一个和第三个元素不受影响：

```html
<planet>Venus</planet>
<planet moons="1">Earth</planet>
<planet moons="2">Mars</planet>
```

属性与属性值必须完全匹配
请注意，这种格式要求必须与属性值完全匹配。

如果属性值包含用空格分隔的值列表，匹配就可能出问题。
请考虑一下的标记片段：

```html
<p class="important warning">This paragraph is a very important warning.</p>
```

如果写成 p[class="important"]，那么这个规则不能匹配示例标记。
要根据具体属性值来选择该元素，必须这样写：

```css
p[class="important warning"] {color: red;}
```

####根据部分属性值选择
如果需要根据属性值中的词列表的某个词进行选择，则需要使用波浪号（~）。
假设您想选择 class 属性中包含 important 的元素，可以用下面这个选择器做到这一点：

```css
p[class~="important"] {color: red;}
```

如果忽略了波浪号，则说明需要完成完全值匹配。

#####部分值属性选择器与点号类名记法的区别
该选择器等价于我们在类选择器中讨论过的点号类名记法。
也就是说，p.important 和 p[class="important"] 应用到 HTML 文档时是等价的。

那么，为什么还要有 "~=" 属性选择器呢？因为它能用于任何属性，而不只是 class。
例如，可以有一个包含大量图像的文档，其中只有一部分是图片。对此，可以使用一个基于 title 文档的部分属性选择器，只选择这些图片：

```css
img[title~="Figure"] {border: 1px solid gray;}
```

这个规则会选择 title 文本包含 "Figure" 的所有图像。没有 title 属性或者 title 属性中不包含 "Figure" 的图像都不会匹配。

#####子串匹配属性选择器
下面为您介绍一个更高级的选择器模块，它是 CSS2 完成之后发布的，其中包含了更多的部分值属性选择器。按照规范的说法，应该称之为“子串匹配属性选择器”。

很多现代浏览器都支持这些选择器，包括 IE7。

下表是对这些选择器的简单总结：

类型|	描述
:--:|:--:
[abc^="def"]|	选择 abc 属性值以 "def" 开头的所有元素
[abc$="def"]|	选择 abc 属性值以 "def" 结尾的所有元素
[abc*="def"]|	选择 abc 属性值中包含子串 "def" 的所有元素

可以想到，这些选择有很多用途。

举例来说，如果希望对指向 W3School 的所有链接应用样式，不必为所有这些链接指定 class，再根据这个类编写样式，而只需编写以下规则：

```css
a[href*="w3school.com.cn"] {color: red;}
```

提示：任何属性都可以使用这些选择器。

####特定属性选择类型
最后为您介绍特定属性选择器。请看下面的例子：

```css
*[lang|="en"] {color: red;}
```

上面这个规则会选择 lang 属性等于 en 或以 en- 开头的所有元素。因此，以下示例标记中的前三个元素将被选中，而不会选择后两个元素：

```html
<p lang="en">Hello!</p>
<p lang="en-us">Greetings!</p>
<p lang="en-au">G'day!</p>
<p lang="fr">Bonjour!</p>
<p lang="cy-en">Jrooana!</p>
```

一般来说，[att|="val"] 可以用于任何属性及其值。
假设一个 HTML 文档中有一系列图片，其中每个图片的文件名都形如 figure-1.jpg 和 figure-2.jpg。就可以使用以下选择器匹配所有这些图像：

```css
img[src|="figure"] {border: 1px solid gray;}
```

当然，这种属性选择器最常见的用途还是匹配语言值。

###CSS 选择器参考手册
选择器|	描述
:--:|:--:
[attribute]|	用于选取带有指定属性的元素。
[attribute=value]|	用于选取带有指定属性和值的元素。
[attribute~=value]|	用于选取属性值中包含指定词汇的元素。
[attribute\|=value]|	用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。
[attribute^=value]|	匹配属性值以指定值开头的每个元素。
[attribute$=value]|	匹配属性值以指定值结尾的每个元素。
[attribute*=value]|	匹配属性值中包含指定值的每个元素。

___