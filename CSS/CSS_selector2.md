#CSS 選擇器
##CSS 後代選擇器
**後代選擇器（descendant selector）又稱為包含選擇器。**
**後代選擇器可以選擇作為某元素後代的元素。**

###根據上下文選擇元素
我們可以定義後代選擇器來創建一些規則，使這些規則在某些文檔結構中起作用，而在另外一些結構中不起作用。
舉例來說，如果您希望只對 h1 元素中的 em 元素應用樣式，可以這樣寫：

```css
h1 em {color:red;}
```

上面這個規則會把作為 h1 元素後代的 em 元素的文本變為 紅色。其他 em 文本（如段落或塊引用中的 em）則不會被這個規則選中：

```html
<h1>This is a <em>important</em> heading</h1>
<p>This is a <em>important</em> paragraph.</p>
```

當然，您也可以在 h1 中找到的每個 em 元素上放一個 class 屬性，但是顯然，後代選擇器的效率更高。

###語法解釋
在後代選擇器中，規則左邊的選擇器一端包括兩個或多個用空格分隔的選擇器。選擇器之間的空格是一種結合符（combinator）。每個空格結合符可以解釋為「... 在 ... 找到」、「... 作為 ... 的一部分」、「... 作為 ... 的後代」，但是要求必須從右向左讀選擇器。

因此，h1 em 選擇器可以解釋為 「作為 h1 元素後代的任何 em 元素」。如果要從左向右讀選擇器，可以換成以下說法：「包含 em 的所有 h1 會把以下樣式應用到該 em」。

###具體應用
後代選擇器的功能極其強大。有了它，可以使 HTML 中不可能實現的任務成為可能。

假設有一個文檔，其中有一個邊欄，還有一個主區。邊欄的背景為藍色，主區的背景為白色，這兩個區都包含鏈接列表。不能把所有鏈接都設置為藍色，因為這樣一來邊欄中的藍色鏈接都無法看到。

解決方法是使用後代選擇器。在這種情況下，可以為包含邊欄的 div 指定值為 sidebar 的 class 屬性，並把主區的 class 屬性值設置為 maincontent。然後編寫以下樣式：

```css
div.sidebar {background:blue;}
div.maincontent {background:white;}
div.sidebar a:link {color:white;}
div.maincontent a:link {color:blue;}
```

有關後代選擇器有一個易被忽視的方面，即兩個元素之間的層次間隔可以是無限的。
例如，如果寫作 ul em，這個語法就會選擇從 ul 元素繼承的所有 em 元素，而不論 em 的嵌套層次多深。

因此，ul em 將會選擇以下標記中的所有 em 元素：

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

##CSS 子元素選擇器
**與後代選擇器相比，子元素選擇器（Child selectors）只能選擇作為某元素子元素的元素。**
###選擇子元素
如果您不希望選擇任意的後代元素，而是希望縮小範圍，只選擇某個元素的子元素，請使用子元素選擇器（Child selector）。
例如，如果您希望選擇只作為 h1 元素子元素的 strong 元素，可以這樣寫：

```css
h1 > strong {color:red;}
```

這個規則會把第一個 h1 下面的兩個 strong 元素變為紅色，但是第二個 h1 中的 strong 不受影響：

```html
<h1>This is <strong>very</strong> <strong>very</strong> important.</h1>
<h1>This is <em>really <strong>very</strong></em> important.</h1>
```

###語法解釋
您應該已經注意到了，子選擇器使用了大於號（子結合符）。
子結合符兩邊可以有空白符，這是可選的。因此，以下寫法都沒有問題：

```css
h1 > strong
h1> strong
h1 >strong
h1>strong
```

如果從右向左讀，選擇器 h1 > strong 可以解釋為「選擇作為 h1 元素子元素的所有 strong 元素」。

###結合後代選擇器和子選擇器
請看下面這個選擇器：

```css
table.company td > p
```

上面的選擇器會選擇作為 td 元素子元素的所有 p 元素，這個 td 元素本身從 table 元素繼承，該 table 元素有一個包含 company 的 class 屬性。

___

##CSS 相鄰兄弟選擇器
**相鄰兄弟選擇器（Adjacent sibling selector）可選擇緊接在另一元素後的元素，且二者有相同父元素。**
###選擇相鄰兄弟
如果需要選擇緊接在另一個元素後的元素，而且二者有相同的父元素，可以使用相鄰兄弟選擇器（Adjacent sibling selector）。
例如，如果要增加緊接在 h1 元素後出現的段落的上邊距，可以這樣寫：

```css
h1 + p {margin-top:50px;}
```

這個選擇器讀作：「選擇緊接在 h1 元素後出現的段落，h1 和 p 元素擁有共同的父元素」。

###語法解釋
相鄰兄弟選擇器使用了加號（+），即相鄰兄弟結合符（Adjacent sibling combinator）。
注釋：與子結合符一樣，相鄰兄弟結合符旁邊可以有空白符。
請看下面這個文檔樹片段：

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

在上面的片段中，div 元素中包含兩個列表：一個無序列表，一個有序列表，每個列表都包含三個列表項。這兩個列表是相鄰兄弟，列表項本身也是相鄰兄弟。不過，第一個列表中的列表項與第二個列表中的列表項不是相鄰兄弟，因為這兩組列表項不屬於同一父元素（最多只能算堂兄弟）。
請記住，用一個結合符只能選擇兩個相鄰兄弟中的第二個元素。請看下面的選擇器：

```css
li + li {font-weight:bold;}
```

上面這個選擇器只會把列表中的第二個和第三個列表項變為粗體。第一個列表項不受影響。

####結合其他選擇器
相鄰兄弟結合符還可以結合其他結合符：

```css
html > body table + ul {margin-top:20px;}
```

這個選擇器解釋為：選擇緊接在 table 元素後出現的所有兄弟 ul 元素，該 table 元素包含在一個 body 元素中，body 元素本身是 html 元素的子元素。

___

##CSS 偽類 (Pseudo-classes)
**CSS 偽類用於向某些選擇器添加特殊的效果。**

###語法
偽類的語法：

```css
selector : pseudo-class {property: value}
```

CSS 類也可與偽類搭配使用。

```css
selector.class : pseudo-class {property: value}
```

###錨偽類
在支持 CSS 的瀏覽器中，鏈接的不同狀態都可以不同的方式顯示，這些狀態包括：活動狀態，已被訪問狀態，未被訪問狀態，和鼠標懸停狀態。

```css
a:link {color: #FF0000}		/* 未訪問的鏈接 */
a:visited {color: #00FF00}	/* 已訪問的鏈接 */
a:hover {color: #FF00FF}	/* 鼠標移動到鏈接上 */
a:active {color: #0000FF}	/* 選定的鏈接 */
```

提示：在 CSS 定義中，a:hover 必須被置於 a:link 和 a:visited 之後，才是有效的。
提示：在 CSS 定義中，a:active 必須被置於 a:hover 之後，才是有效的。
提示：偽類名稱對大小寫不敏感。

###偽類與 CSS 類
偽類可以與 CSS 類配合使用：

```html
a.red : visited {color: #FF0000}

<a class="red" href="css_syntax.asp">CSS Syntax</a>
```

假如上面的例子中的鏈接被訪問過，那麼它將顯示為紅色。

###CSS2 - :first-child 偽類
您可以使用 :first-child 偽類來選擇元素的第一個子元素。這個特定偽類很容易遭到誤解，所以有必要舉例來說明。考慮以下標記：

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

在上面的例子中，作為第一個元素的元素包括第一個 p、第一個 li 和 strong 和 em 元素。
給定以下規則：

```css
p:first-child {font-weight: bold;}
li:first-child {text-transform:uppercase;}
```

第一個規則將作為某元素第一個子元素的所有 p 元素設置為粗體。第二個規則將作為某個元素（在 HTML 中，這肯定是 ol 或 ul 元素）第一個子元素的所有 li 元素變成大寫。

提示：最常見的錯誤是認為 p:first-child 之類的選擇器會選擇 p 元素的第一個子元素。

注釋：必須聲明 `<!DOCTYPE>`，這樣 :first-child 才能在 IE 中生效。
為了使您更透徹地理解 :first-child 偽類，我們另外提供了 3 個例子：

例子 1 - 匹配第一個 `<p>` 元素
在下面的例子中，選擇器匹配作為任何元素的第一個子元素的 p 元素：

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

例子 2 - 匹配所有 `<p>` 元素中的第一個 `<i>` 元素
在下面的例子中，選擇器匹配所有 `<p>` 元素中的第一個 `<i>` 元素：

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

例子 3 - 匹配所有作為第一個子元素的 `<p>` 元素中的所有 `<i>` 元素
在下面的例子中，選擇器匹配所有作為元素的第一個子元素的 `<p>` 元素中的所有 `<i>` 元素：

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

###CSS2 - :lang 偽類
:lang 偽類使你有能力為不同的語言定義特殊的規則。在下面的例子中，:lang 類為屬性值為 no 的 q 元素定義引號的類型：

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

###偽類
**W3C**："W3C" 列指示出該屬性在哪個 CSS 版本中定義（CSS1 還是 CSS2）。

屬性|	描述|	CSS
:--:|:--:|:--:
:active	|向被激活的元素添加樣式。	|1
:focus|	向擁有鍵盤輸入焦點的元素添加樣式。|	2
:hover|	當鼠標懸浮在元素上方時，向元素添加樣式。	|1
:link|	向未被訪問的鏈接添加樣式。	|1
:visited|	向已被訪問的鏈接添加樣式。	|1
:first-child|	向元素的第一個子元素添加樣式。	|2
:lang|	向帶有指定 lang 屬性的元素添加樣式。	|2

___

##CSS 偽元素 (Pseudo-elements)
**CSS 偽元素用於向某些選擇器設置特殊效果。**

###語法
偽元素的語法：

```css
selector:pseudo-element {property:value;}
```
CSS 類也可以與偽元素配合使用：

```css
selector.class:pseudo-element {property:value;}
```

##:first-line 偽元素
"first-line" 偽元素用於向文本的首行設置特殊樣式。
在下面的例子中，瀏覽器會根據 "first-line" 偽元素中的樣式對 p 元素的第一行文本進行格式化：

實例

```css
p:first-line
  {
  color:#ff0000;
  font-variant:small-caps;
  }
```

注釋："first-line" 偽元素只能用於塊級元素。
注釋：下面的屬性可應用於 "first-line" 偽元素：

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

###:first-letter 偽元素
"first-letter" 偽元素用於向文本的首字母設置特殊樣式：

```css
p:first-letter
  {
  color:#ff0000;
  font-size:xx-large;
  }
```

注釋："first-letter" 偽元素只能用於塊級元素。
注釋：下面的屬性可應用於 "first-letter" 偽元素：

* font
* color
* background
* margin
* padding
* border
* text-decoration
* vertical-align(僅當 float 為 none 時)
* text-transform
* line-height
* float
* clear

###偽元素和 CSS 類
偽元素可以與 CSS 類配合使用：

```html
p.article:first-letter
  {
  color: #FF0000;
  }

<p class="article">This is a paragraph in an article。</p>
```
上面的例子會使所有 class 為 article 的段落的首字母變為紅色。

###多重偽元素
可以結合多個偽元素來使用。

在下面的例子中，段落的第一個字母將顯示為紅色，其字體大小為 xx-large。第一行中的其餘文本將為藍色，並以小型大寫字母顯示。段落中的其餘文本將以默認字體大小和顏色來顯示：

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

###CSS2 - :before 偽元素
":before" 偽元素可以在元素的內容前面插入新內容。
下面的例子在每個 `<h1>` 元素前面插入一幅圖片：

```css
h1:before
  {
  content:url(logo.gif);
  }
```

###CSS2 - :after 偽元素
":after" 偽元素可以在元素的內容之後插入新內容。
下面的例子在每個 `<h1>` 元素後面插入一幅圖片：

```css
h1:after
  {
  content:url(logo.gif);
  }
```

###偽元素
**W3C**："W3C" 列指示出該屬性在哪個 CSS 版本中定義（CSS1 還是 CSS2）。

屬性|	描述|	CSS
:--:|:--:|:--:
:first-letter|	向文本的第一個字母添加特殊樣式。	|1
:first-line|	向文本的首行添加特殊樣式。	|1
:before|	在元素之前添加內容。	|2
:after|	在元素之後添加內容。	|2