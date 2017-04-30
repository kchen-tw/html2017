#CSS背景
**CSS 允许应用纯色作为背景，也允许使用背景图像创建相当复杂的效果。
CSS 在这方面的能力远远在 HTML 之上。**
##背景色
可以使用 background-color 属性为元素设置背景色。这个属性接受任何合法的颜色值。
这条规则把元素的背景设置为灰色：
`p {background-color: gray;}`
如果您希望背景色从元素中的文本向外少有延伸，只需增加一些内边距：
`p {background-color: gray; padding: 20px;}`

可以为所有元素设置背景色，这包括 body 一直到 em 和 a 等行内元素。

background-color 不能继承，其默认值是 transparent。transparent 有“透明”之意。也就是说，如果一个元素没有指定背景色，那么背景就是透明的，这样其祖先元素的背景才能可见。

##背景图像
要把图像放入背景，需要使用 background-image 属性。background-image 属性的默认值是 none，表示背景上没有放置任何图像。

如果需要设置一个背景图像，必须为这个属性设置一个 URL 值：
`body {background-image: url(/i/eg_bg_04.gif);}`
大多数背景都应用到 body 元素，不过并不仅限于此。
下面例子为一个段落应用了一个背景，而不会对文档的其他部分应用背景：
`p.flower {background-image: url(/i/eg_bg_03.gif);}`
您甚至可以为行内元素设置背景图像，下面的例子为一个链接设置了背景图像：
`a.radio {background-image: url(/i/eg_bg_07.gif);}`

理论上讲，甚至可以向 textareas 和 select 等替换元素的背景应用图像，不过并不是所有用户代理都能很好地处理这种情况。
另外还要补充一点，background-image 也不能继承。事实上，所有背景属性都不能继承。

##背景重复
如果需要在页面上对背景图像进行平铺，可以使用 background-repeat 属性。

属性值 repeat 导致图像在水平垂直方向上都平铺，就像以往背景图像的通常做法一样。repeat-x 和 repeat-y 分别导致图像只在水平或垂直方向上重复，no-repeat 则不允许图像在任何方向上平铺。

默认地，背景图像将从一个元素的左上角开始。请看下面的例子：

```css
body
  { 
  background-image: url(/i/eg_bg_03.gif);
  background-repeat: repeat-y;
  }
```

##背景定位
可以利用 background-position 属性改变图像在背景中的位置。
下面的例子在 body 元素中将一个背景图像居中放置：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:center;
  }
```
为 background-position 属性提供值有很多方法。首先，可以使用一些关键字：top、bottom、left、right 和 center。通常，这些关键字会成对出现，不过也不总是这样。还可以使用长度值，如 100px 或 5cm，最后也可以使用百分数值。不同类型的值对于背景图像的放置稍有差异。

关键字
图像放置关键字最容易理解，其作用如其名称所表明的。例如，top right 使图像放置在元素内边距区的右上角。
根据规范，位置关键字可以按任何顺序出现，只要保证不超过两个关键字 - 一个对应水平方向，另一个对应垂直方向。
如果只出现一个关键字，则认为另一个关键字是 center。
所以，如果希望每个段落的中部上方出现一个图像，只需声明如下：

```css
p
  { 
    background-image:url('bgimg.gif');
    background-repeat:no-repeat;
    background-position:top;
  }
```

下面是等价的位置关键字：

单一关键字|	等价的关键字
:--:|:--:
center|	center center
top	|top center 或 center top
bottom	|bottom center 或 center bottom
right	|right center 或 center right
left	|left center 或 center left

百分数值
百分数值的表现方式更为复杂。假设你希望用百分数值将图像在其元素中居中，这很容易：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
  }
```
这会导致图像适当放置，其中心与其元素的中心对齐。换句话说，百分数值同时应用于元素和图像。也就是说，图像中描述为 50% 50% 的点（中心点）与元素中描述为 50% 50% 的点（中心点）对齐。

如果图像位于 0% 0%，其左上角将放在元素内边距区的左上角。如果图像位置是 100% 100%，会使图像的右下角放在右边距的右下角。

因此，如果你想把一个图像放在水平方向 2/3、垂直方向 1/3 处，可以这样声明：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:66% 33%;
  }
```
如果只提供一个百分数值，所提供的这个值将用作水平值，垂直值将假设为 50%。这一点与关键字类似。

background-position 的默认值是 0% 0%，在功能上相当于 top left。这就解释了背景图像为什么总是从元素内边距区的左上角开始平铺，除非您设置了不同的位置值。

长度值
长度值解释的是元素内边距区左上角的偏移。偏移点是图像的左上角。
比如，如果设置值为 50px 100px，图像的左上角将在元素内边距区左上角向右 50 像素、向下 100 像素的位置上：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50px 100px;
  }
```
注意，这一点与百分数值不同，因为偏移只是从一个左上角到另一个左上角。也就是说，图像的左上角与 background-position 声明中的指定的点对齐。

##背景关联
如果文档比较长，那么当文档向下滚动时，背景图像也会随之滚动。当文档滚动到超过图像的位置时，图像就会消失。
您可以通过 background-attachment 属性防止这种滚动。通过这个属性，可以声明图像相对于可视区是固定的（fixed），因此不会受到滚动的影响：

```css
body 
  {
    background-image:url(/i/eg_bg_02.gif);
    background-repeat:no-repeat;
    background-attachment:fixed
  }
```

background-attachment 属性的默认值是 scroll，也就是说，在默认的情况下，背景会随文档滚动。

##CSS 背景属性

属性|	描述
:--:|:--:
background|	简写属性，作用是将背景属性设置在一个声明中。
background-attachment|	背景图像是否固定或者随着页面的其余部分滚动。
background-color	|设置元素的背景颜色。
background-image	|把图像设置为背景。
background-position	|设置背景图像的起始位置。
background-repeat	|设置背景图像是否及如何重复。
___

#CSS文本
**CSS 文本属性可定义文本的外观。
通过文本属性，您可以改变文本的颜色、字符间距，对齐文本，装饰文本，对文本进行缩进，等等。**
##缩进文本
把 Web 页面上的段落的第一行缩进，这是一种最常用的文本格式化效果。
CSS 提供了 text-indent 属性，该属性可以方便地实现文本缩进。

通过使用 text-indent 属性，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值。
这个属性最常见的用途是将段落的首行缩进，下面的规则会使所有段落的首行缩进 5 em：
`p {text-indent: 5em;}`

注意：一般来说，可以为所有块级元素应用 text-indent，但无法将该属性应用于行内元素，图像之类的替换元素上也无法应用 text-indent 属性。不过，如果一个块级元素（比如段落）的首行中有一个图像，它会随该行的其余文本移动。
提示：如果想把一个行内元素的第一行“缩进”，可以用左内边距或外边距创造这种效果。

使用负值
text-indent 还可以设置为负值。利用这种技术，可以实现很多有趣的效果，比如“悬挂缩进”，即第一行悬挂在元素中余下部分的左边：
`p {text-indent: -5em;}`
不过在为 text-indent 设置负值时要当心，如果对一个段落设置了负值，那么首行的某些文本可能会超出浏览器窗口的左边界。为了避免出现这种显示问题，建议针对负缩进再设置一个外边距或一些内边距：
`p {text-indent: -5em; padding-left: 5em;}`

使用百分比值
text-indent 可以使用所有长度单位，包括百分比值。
百分数要相对于缩进元素父元素的宽度。换句话说，如果将缩进值设置为 20%，所影响元素的第一行会缩进其父元素宽度的 20%。
在下例中，缩进值是父元素的 20%，即 100 个像素：

```html
div {width: 500px;}
p {text-indent: 20%;}

<div>
<p>this is a paragragh</p>
</div>
```

继承
text-indent 属性可以继承，请考虑如下标记：

```html
div#outer {width: 500px;}
div#inner {text-indent: 10%;}
p {width: 200px;}

<div id="outer">
<div id="inner">some text. some text. some text.
<p>this is a paragragh.</p>
</div>
</div>
```

以上标记中的段落也会缩进 50 像素，这是因为这个段落继承了 id 为 inner 的 div 元素的缩进值。

##水平对齐
text-align 是一个基本的属性，它会影响一个元素中的文本行互相之间的对齐方式。它的前 3 个值相当直接，不过第 4 个和第 5 个则略有些复杂。

值 left、right 和 center 会导致元素中的文本分别左对齐、右对齐和居中。

西方语言都是从左向右读，所有 text-align 的默认值是 left。文本在左边界对齐，右边界呈锯齿状（称为“从左到右”文本）。对于希伯来语和阿拉伯语之类的的语言，text-align 则默认为 right，因为这些语言从右向左读。不出所料，center 会使每个文本行在元素中居中。

提示：将块级元素或表元素居中，要通过在这些元素上适当地设置左、右外边距来实现。

##text-align:center 与 `<CENTER>`
您可能会认为 text-align:center 与 `<CENTER>` 元素的作用一样，但实际上二者大不相同。
`<CENTER>` 不仅影响文本，还会把整个元素居中。text-align 不会控制元素的对齐，而只影响内部内容。元素本身不会从一段移到另一端，只是其中的文本受影响。

##justify
最后一个水平对齐属性是 justify。

在两端对齐文本中，文本行的左右两端都放在父元素的内边界上。然后，调整单词和字母间的间隔，使各行的长度恰好相
等。您也许已经注意到了，两端对齐文本在打印领域很常见。

需要注意的是，要由用户代理（而不是 CSS）来确定两端对齐文本如何拉伸，以填满父元素左右边界之间的空间。如需了解详情，请参阅 CSS text-align 属性参考页。

##字间隔
word-spacing 属性可以改变字（单词）之间的标准间隔。其默认值 normal 与设置值为 0 是一样的。

word-spacing 属性接受一个正长度值或负长度值。如果提供一个正长度值，那么字之间的间隔就会增加。为 word-spacing 设置一个负值，会把它拉近：

```html
p.spread {word-spacing: 30px;}
p.tight {word-spacing: -0.5em;}

<p class="spread">
This is a paragraph. The spaces between words will be increased.
</p>

<p class="tight">
This is a paragraph. The spaces between words will be decreased.
</p>
```

注释：如需深入理解 CSS 对“字”（word）的定义，请访问 CSS word-spacing 属性参考页。

##字母间隔
letter-spacing 属性与 word-spacing 的区别在于，字母间隔修改的是字符或字母之间的间隔。

与 word-spacing 属性一样，letter-spacing 属性的可取值包括所有长度。默认关键字是 normal（这与 letter-spacing:0 相同）。输入的长度值会使字母之间的间隔增加或减少指定的量：

```html
h1 {letter-spacing: -0.5em}
h4 {letter-spacing: 20px}

<h1>This is header 1</h1>
<h4>This is header 4</h4>
```

##字符转换
text-transform 属性处理文本的大小写。这个属性有 4 个值：
* none
* uppercase
* lowercase
* capitalize
默认值 none 对文本不做任何改动，将使用源文档中的原有大小写。顾名思义，uppercase 和 lowercase 将文本转换为全大写和全小写字符。最后，capitalize 只对每个单词的首字母大写。

作为一个属性，text-transform 可能无关紧要，不过如果您突然决定把所有 h1 元素变为大写，这个属性就很有用。不必单独地修改所有 h1 元素的内容，只需使用 text-transform 为你完成这个修改：
`h1 {text-transform: uppercase}`
使用 text-transform 有两方面的好处。首先，只需写一个简单的规则来完成这个修改，而无需修改 h1 元素本身。其次，如果您以后决定将所有大小写再切换为原来的大小写，可以更容易地完成修改。

##文本装饰
接下来，我们讨论 text-decoration 属性，这是一个很有意思的属性，它提供了很多非常有趣的行为。

text-decoration 有 5 个值：
* none
* underline
* overline
* line-through
* blink

不出所料，underline 会对元素加下划线，就像 HTML 中的 U 元素一样。overline 的作用恰好相反，会在文本的顶端画一个上划线。值 line-through 则在文本中间画一个贯穿线，等价于 HTML 中的 S 和 strike 元素。blink 会让文本闪烁，类似于 Netscape 支持的颇招非议的 blink 标记。

none 值会关闭原本应用到一个元素上的所有装饰。通常，无装饰的文本是默认外观，但也不总是这样。例如，链接默认地会有下划线。如果您希望去掉超链接的下划线，可以使用以下 CSS 来做到这一点：
`a {text-decoration: none;}`

注意：如果显式地用这样一个规则去掉链接的下划线，那么锚与正常文本之间在视觉上的唯一差别就是颜色（至少默认是这样的，不过也不能完全保证其颜色肯定有区别）。

还可以在一个规则中结合多种装饰。如果希望所有超链接既有下划线，又有上划线，则规则如下：
`a:link a:visited {text-decoration: underline overline;}`
不过要注意的是，如果两个不同的装饰都与同一元素匹配，胜出规则的值会完全取代另一个值。请考虑以下的规则：
`h2.stricken {text-decoration: line-through;}`
`h2 {text-decoration: underline overline;}`
对于给定的规则，所有 class 为 stricken 的 h2 元素都只有一个贯穿线装饰，而没有下划线和上划线，因为 text-decoration 值会替换而不是累积起来。

##处理空白符
white-space 属性会影响到用户代理对源文档中的空格、换行和 tab 字符的处理。

通过使用该属性，可以影响浏览器处理字之间和文本行之间的空白符的方式。从某种程度上讲，默认的 XHTML 处理已经完成了空白符处理：它会把所有空白符合并为一个空格。所以给定以下标记，它在 Web 浏览器中显示时，各个字之间只会显示一个空格，同时忽略元素中的换行：

```html
<p>  This     paragraph has    many
    spaces           in it.</p>
```
可以用以下声明显式地设置这种默认行为：
`p {white-space: normal;}`

上面的规则告诉浏览器按照平常的做法去处理：丢掉多余的空白符。如果给定这个值，换行字符（回车）会转换为空格，一行中多个空格的序列也会转换为一个空格。

##值 pre
不过，如果将 white-space 设置为 pre，受这个属性影响的元素中，空白符的处理就有所不同，其行为就像 XHTML 的 pre 元素一样；空白符不会被忽略。

如果 white-space 属性的值为 pre，浏览器将会注意额外的空格，甚至回车。在这个方面，而且仅在这个方面，任何元素都可以相当于一个 pre 元素。

注意：经测试，IE 7 以及更早版本的浏览器不支持该值，因此请使用非 IE 的浏览器来查看上面的实例。

##值 nowrap
与之相对的值是 nowrap，它会防止元素中的文本换行，除非使用了一个 br 元素。在 CSS 中使用 nowrap 非常类似于 HTML 4 中用 `<td nowrap>` 将一个表单元格设置为不能换行，不过 white-space 值可以应用到任何元素。

##值 pre-wrap 和 pre-line
CSS2.1 引入了值 pre-wrap 和 pre-line，这在以前版本的 CSS 中是没有的。这些值的作用是允许创作人员更好地控制空白符处理。

如果元素的 white-space 设置为 pre-wrap，那么该元素中的文本会保留空白符序列，但是文本行会正常地换行。如果设置为这个值，源文本中的行分隔符以及生成的行分隔符也会保留。pre-line 与 pre-wrap 相反，会像正常文本中一样合并空白符序列，但保留换行符。

注意：我们在 IE7 和 FireFox2.0 浏览器中测试了上面的两个实例，但是结果是，值 pre-wrap 和 pre-line 都没有得到很好的支持。

总结
下面的表格总结了 white-space 属性的行为：

值|	空白符|	换行符|	自动换行
:--:|:--:|:--:|:--:
pre-line	|合并|	保留|	允许
normal	|合并	|忽略	|允许
nowrap	|合并|	忽略|	不允许
pre	|保留	|保留|	不允许
pre-wrap|	保留|	保留|	允许

##文本方向
如果您阅读的是英文书籍，就会从左到右、从上到下地阅读，这就是英文的流方向。不过，并不是所有语言都如此。我们知道古汉语就是从右到左来阅读的，当然还包括希伯来语和阿拉伯语等等。CSS2 引入了一个属性来描述其方向性。

direction 属性影响块级元素中文本的书写方向、表中列布局的方向、内容水平填充其元素框的方向、以及两端对齐元素中最后一行的位置。

注释：对于行内元素，只有当 unicode-bidi 属性设置为 embed 或 bidi-override 时才会应用 direction 属性。

direction 属性有两个值：ltr 和 rtl。大多数情况下，默认值是 ltr，显示从左到右的文本。如果显示从右到左的文本，应使用值 rtl。


##CSS 文本属性

属性|	描述
:--:|:--:
color|	设置文本颜色
direction|	设置文本方向。
line-height|	设置行高。
letter-spacing|	设置字符间距。
text-align	|对齐元素中的文本。
text-decoration	|向文本添加修饰。
text-indent	|缩进元素中文本的首行。
text-shadow	|设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。
text-transform	|控制元素中的字母。
unicode-bidi	|设置文本方向。
white-space	|设置元素中空白的处理方式。
word-spacing	|设置字间距。

___

#CSS 字体

**CSS 字体属性定义文本的字体系列、大小、加粗、风格（如斜体）和变形（如小型大写字母）。**
##CSS 字体系列

在 CSS 中，有两种不同类型的字体系列名称：

* 通用字体系列 - 拥有相似外观的字体系统组合（比如 "Serif" 或 "Monospace"）
* 特定字体系列 - 具体的字体系列（比如 "Times" 或 "Courier"）

除了各种特定的字体系列外，CSS 定义了 5 种通用字体系列：

* Serif 字体
* Sans-serif 字体
* Monospace 字体
* Cursive 字体
* Fantasy 字体

如果需要了解更多有关字体系列的知识，请阅读 CSS 字体系列。

##指定字体系列
使用 font-family 属性 定义文本的字体系列。

使用通用字体系列
如果你希望文档使用一种 sans-serif 字体，但是你并不关心是哪一种字体，以下就是一个合适的声明：
`body {font-family: sans-serif;}`

这样用户代理就会从 sans-serif 字体系列中选择一个字体（如 Helvetica），并将其应用到 body 元素。因为有继承，这种字体选择还将应用到 body 元素中包含的所有元素，除非有一种更特定的选择器将其覆盖。

指定字体系列
除了使用通用的字体系列，您还可以通过 font-family 属性设置更具体的字体。
下面的例子为所有 h1 元素设置了 Georgia 字体：
`h1 {font-family: Georgia;}`

这样的规则同时会产生另外一个问题，如果用户代理上没有安装 Georgia 字体，就只能使用用户代理的默认字体来显示 h1 元素。
我们可以通过结合特定字体名和通用字体系列来解决这个问题：
`h1 {font-family: Georgia, serif;}`

如果读者没有安装 Georgia，但安装了 Times 字体（serif 字体系列中的一种字体），用户代理就可能对 h1 元素使用 Times。尽管 Times 与 Georgia 并不完全匹配，但至少足够接近。

因此，我们建议在所有 font-family 规则中都提供一个通用字体系列。这样就提供了一条后路，在用户代理无法提供与规则匹配的特定字体时，就可以选择一个候选字体。

如果您对字体非常熟悉，也可以为给定的元素指定一系列类似的字体。要做到这一点，需要把这些字体按照优先顺序排列，然后用逗号进行连接：

```css
p {font-family: Times, TimesNR, 'New Century Schoolbook',
     Georgia, 'New York', serif;}
```

根据这个列表，用户代理会按所列的顺序查找这些字体。如果列出的所有字体都不可用，就会简单地选择一种可用的 serif 字体。

使用引号
您也许已经注意到了，上面的例子中使用了单引号。只有当字体名中有一个或多个空格（比如 New York），或者如果字体名包括 # 或 $ 之类的符号，才需要在 font-family 声明中加引号。

单引号或双引号都可以接受。但是，如果把一个 font-family 属性放在 HTML 的 style 属性中，则需要使用该属性本身未使用的那种引号：

```html
<p style="font-family: Times, TimesNR, 'New Century Schoolbook', Georgia,
 'New York', serif;">...</p>
```

##字体风格
font-style 属性最常用于规定斜体文本。
该属性有三个值：

* normal - 文本正常显示
* italic - 文本斜体显示
* oblique - 文本倾斜显示

实例

```css
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

##italic 和 oblique 的区别
font-style 非常简单：用于在 normal 文本、italic 文本和 oblique 文本之间选择。唯一有点复杂的是明确 italic 文本和 oblique 文本之间的差别。

斜体（italic）是一种简单的字体风格，对每个字母的结构有一些小改动，来反映变化的外观。与此不同，倾斜（oblique）文本则是正常竖直文本的一个倾斜版本。

通常情况下，italic 和 oblique 文本在 web 浏览器中看上去完全一样。

##字体变形
font-variant 属性可以设定小型大写字母。
小型大写字母不是一般的大写字母，也不是小写字母，这种字母采用不同大小的大写字母。

实例
`p {font-variant:small-caps;}`

##字体加粗
font-weight 属性设置文本的粗细。

使用 bold 关键字可以将文本设置为粗体。

关键字 100 ~ 900 为字体指定了 9 级加粗度。如果一个字体内置了这些加粗级别，那么这些数字就直接映射到预定义的级别，100 对应最细的字体变形，900 对应最粗的字体变形。数字 400 等价于 normal，而 700 等价于 bold。

如果将元素的加粗设置为 bolder，浏览器会设置比所继承值更粗的一个字体加粗。与此相反，关键词 lighter 会导致浏览器将加粗度下移而不是上移。
实例

```css
p.normal {font-weight:normal;}
p.thick {font-weight:bold;}
p.thicker {font-weight:900;}
```

##字体大小
font-size 属性设置文本的大小。
有能力管理文本的大小在 web 设计领域很重要。但是，您不应当通过调整文本大小使段落看上去像标题，或者使标题看上去像段落。

请始终使用正确的 HTML 标题，比如使用 `<h1>` - `<h6>` 来标记标题，使用 `<p>` 来标记段落。
font-size 值可以是绝对或相对值。

绝对值：

* 将文本设置为指定的大小
* 不允许用户在所有浏览器中改变文本大小（不利于可用性）
* 绝对大小在确定了输出的物理尺寸时很有用

相对大小：

* 相对于周围的元素来设置大小
* 允许用户在浏览器改变文本大小

注意：如果您没有规定字体大小，普通文本（比如段落）的默认大小是 16 像素 (16px=1em)。

使用像素来设置字体大小
通过像素设置文本大小，可以对文本大小进行完全控制：
实例

```css
h1 {font-size:60px;}
h2 {font-size:40px;}
p {font-size:14px;}
```

在 Firefox, Chrome, and Safari 中，可以重新调整以上例子的文本大小，但是在 Internet Explorer 中不行。
虽然可以通过浏览器的缩放工具调整文本大小，但是这实际上是对整个页面的调整，而不仅限于文本。

##使用 em 来设置字体大小

如果要避免在 Internet Explorer 中无法调整文本的问题，许多开发者使用 em 单位代替 pixels。

W3C 推荐使用 em 尺寸单位。

1em 等于当前的字体尺寸。如果一个元素的 font-size 为 16 像素，那么对于该元素，1em 就等于 16 像素。在设置字体大小时，em 的值会相对于父元素的字体大小改变。

浏览器中默认的文本大小是 16 像素。因此 1em 的默认尺寸是 16 像素。

可以使用下面这个公式将像素转换为 em：pixels/16=em
（注：16 等于父元素的默认字体大小，假设父元素的 font-size 为 20px，那么公式需改为：pixels/20=em）
实例

```css
h1 {font-size:3.75em;} /* 60px/16=3.75em */
h2 {font-size:2.5em;}  /* 40px/16=2.5em */
p {font-size:0.875em;} /* 14px/16=0.875em */
```

在上面的例子中，以 em 为单位的文本大小与前一个例子中以像素计的文本是相同的。不过，如果使用 em 单位，则可以在所有浏览器中调整文本大小。

不幸的是，在 IE 中仍存在问题。在重设文本大小时，会比正常的尺寸更大或更小。
结合使用百分比和 EM

在所有浏览器中均有效的方案是为 body 元素（父元素）以百分比设置默认的 font-size 值：
实例

```css
body {font-size:100%;}
h1 {font-size:3.75em;}
h2 {font-size:2.5em;}
p {font-size:0.875em;}
```

我们的代码非常有效。在所有浏览器中，可以显示相同的文本大小，并允许所有浏览器缩放文本的大小。

##CSS 字体属性

属性|	描述
:--:|:--:
font|	简写属性。作用是把所有针对字体的属性设置在一个声明中。
font-family|	设置字体系列。
font-size|	设置字体的尺寸。
font-size-adjust|	当首选字体不可用时，对替换字体进行智能缩放。（CSS2.1 已删除该属性。）
font-stretch	|对字体进行水平拉伸。（CSS2.1 已删除该属性。）
font-style|	设置字体风格。
font-variant|	以小型大写字体或者正常字体显示文本。
font-weight|	设置字体的粗细。

___

#CSS 链接
**我们能够以不同的方法为链接设置样式。**

##设置链接的样式
能够设置链接样式的 CSS 属性有很多种（例如 color, font-family, background 等等）。
链接的特殊性在于能够根据它们所处的状态来设置它们的样式。
链接的四种状态：

* a:link - 普通的、未被访问的链接
* a:visited - 用户已访问的链接
* a:hover - 鼠标指针位于链接的上方
* a:active - 链接被点击的时刻

实例

```css
a:link {color:#FF0000;}		/* 未被访问的链接 */
a:visited {color:#00FF00;}	/* 已被访问的链接 */
a:hover {color:#FF00FF;}	/* 鼠标指针移动到链接上 */
a:active {color:#0000FF;}	/* 正在被点击的链接 */
```

当为链接的不同状态设置样式时，请按照以下次序规则：

* a:hover 必须位于 a:link 和 a:visited 之后
* a:active 必须位于 a:hover 之后

##常见的链接样式
在上面的例子中，链接根据其状态改变颜色。
让我们看看其他几种常见的设置链接样式的方法：

###文本修饰
text-decoration 属性大多用于去掉链接中的下划线：

实例

```css
a:link {text-decoration:none;}
a:visited {text-decoration:none;}
a:hover {text-decoration:underline;}
a:active {text-decoration:underline;}
```

###背景色
background-color 属性规定链接的背景色：

实例

```css
a:link {background-color:#B2FF99;}
a:visited {background-color:#FFFF85;}
a:hover {background-color:#FF704D;}
a:active {background-color:#FF704D;}
```
___

#CSS 列表
**CSS 列表属性允许你放置、改变列表项标志，或者将图像作为列表项标志。**
##CSS 列表
从某种意义上讲，不是描述性的文本的任何内容都可以认为是列表。人口普查、太阳系、家谱、参观菜单，甚至你的所有朋友都可以表示为一个列表或者是列表的列表。

由于列表如此多样，这使得列表相当重要，所以说，CSS 中列表样式不太丰富确实是一大憾事。

###列表类型
要影响列表的样式，最简单（同时支持最充分）的办法就是改变其标志类型。

例如，在一个无序列表中，列表项的标志 (marker) 是出现在各列表项旁边的圆点。在有序列表中，标志可能是字母、数字或另外某种计数体系中的一个符号。

要修改用于列表项的标志类型，可以使用属性 list-style-type：

```css
ul {list-style-type : square}
```

上面的声明把无序列表中的列表项标志设置为方块。

###列表项图像
有时，常规的标志是不够的。你可能想对各标志使用一个图像，这可以利用 list-style-image 属性做到：

```css
ul li {list-style-image : url(xxx.gif)}
```
只需要简单地使用一个 url() 值，就可以使用图像作为标志。

###列表标志位置
CSS2.1 可以确定标志出现在列表项内容之外还是内容内部。这是利用 list-style-position 完成的。

###简写列表样式
为简单起见，可以将以上 3 个列表样式属性合并为一个方便的属性：list-style，就像这样：

```css
li {list-style : url(example.gif) square inside}
```

list-style 的值可以按任何顺序列出，而且这些值都可以忽略。只要提供了一个值，其它的就会填入其默认值。

##CSS 列表属性(list)

属性|	描述
:--:|:--:
list-style|	简写属性。用于把所有用于列表的属性设置于一个声明中。
list-style-image|	将图象设置为列表项标志。
list-style-position|	设置列表中列表项标志的位置。
list-style-type|	设置列表项标志的类型。

___

#CSS 表格
**CSS 表格属性可以帮助您极大地改善表格的外观。**
##表格边框
如需在 CSS 中设置表格边框，请使用 border 属性。
下面的例子为 table、th 以及 td 设置了蓝色边框：

```css
table, th, td
  {
  border: 1px solid blue;
  }
```

请注意，上例中的表格具有双线条边框。这是由于 table、th 以及 td 元素都有独立的边框。
如果需要把表格显示为单线条边框，请使用 border-collapse 属性。

##折叠边框
border-collapse 属性设置是否将表格边框折叠为单一边框：

```css
table
  {
  border-collapse:collapse;
  }

table,th, td
  {
  border: 1px solid black;
  }
```

##表格宽度和高度
通过 width 和 height 属性定义表格的宽度和高度。
下面的例子将表格宽度设置为 100%，同时将 th 元素的高度设置为 50px：

```css
table
  {
  width:100%;
  }

th
  {
  height:50px;
  }
```

##表格文本对齐
text-align 和 vertical-align 属性设置表格中文本的对齐方式。
text-align 属性设置水平对齐方式，比如左对齐、右对齐或者居中：

```css
td
  {
  text-align:right;
  }
```

vertical-align 属性设置垂直对齐方式，比如顶部对齐、底部对齐或居中对齐：

```css
td
  {
  height:50px;
  vertical-align:bottom;
  }
```

##表格内边距
如需控制表格中内容与边框的距离，请为 td 和 th 元素设置 padding 属性：

```css
td
  {
  padding:15px;
  }
```

##表格颜色
下面的例子设置边框的颜色，以及 th 元素的文本和背景颜色：

```css
table, td, th
  {
  border:1px solid green;
  }

th
  {
  background-color:green;
  color:white;
  }
```

##CSS Table 属性
属性|	描述
:--:|:--:
border-collapse|	设置是否把表格边框合并为单一的边框。
border-spacing|	设置分隔单元格边框的距离。
caption-side|	设置表格标题的位置。
empty-cells|	设置是否显示表格中的空单元格。
table-layout|	设置显示单元、行和列的算法。

___

#CSS 轮廓
**轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。**
**CSS outline 属性规定元素轮廓的样式、颜色和宽度。**


##CSS 边框属性
"CSS" 列中的数字指示哪个 CSS 版本定义了该属性。

属性|	描述|	CSS
:--:|:--:|:--:
outline	|在一个声明中设置所有的轮廓属性。	|2
outline-color|	设置轮廓的颜色。	|2
outline-style|	设置轮廓的样式。	|2
outline-width|	设置轮廓的宽度。	|2

