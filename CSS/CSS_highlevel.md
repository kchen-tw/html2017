##CSS 水平對齊
在 CSS 中，可以使用多種屬性來水平對齊元素。
###對齊塊元素
塊元素指的是佔據全部可用寬度的元素，並且在其前後都會換行。
塊元素的例子：

```html
<h1>
<p>
<div>
```

在本教程中，我們將向您展示出於佈局目的如何水平對齊塊級元素。

###使用 margin 屬性來水平對齊
可通過將左和右外邊距設置為 "auto"，來對齊塊元素。

注釋：除非已經聲明瞭 !DOCTYPE，否則使用 margin:auto 在 IE8 以及更早的版本中是無效的。

把左和右外邊距設置為 auto，規定的是均等地分配可用的外邊距。結果就是居中的元素：
實例

```css
.center
{
margin-left:auto;
margin-right:auto;
width:70%;
background-color:#b0e0e6;
}
```

提示：如果寬度是 100%，則對齊沒有效果。

注釋：在 IE5 中，對於塊元素存在一個外邊距處理方面的 BUG。如需使上面的例子在 IE5 中有效，請添加一些額外的代碼。

###使用 position 屬性進行左和右對齊
對齊元素的方法之一是使用絕對定位：
實例

```css
.right
{
position:absolute;
right:0px;
width:300px;
background-color:#b0e0e6;
}
```
注釋：絕對定位元素會被從正常流中刪除，並且能夠交疊元素。

###跨瀏覽器兼容性問題
當像這樣對齊元素時，對 `<body>` 元素的外邊距和內邊距進行預定義是一個好主意。這樣可以避免在不同的瀏覽器中出現可見的差異。

當使用 position 屬性時，IE8 以及更早的版本存在一個問題。如果容器元素（在我們的案例中是 `<div class="container">`）設置了指定的寬度，並且省略了 !DOCTYPE 聲明，那麼 IE8 以及更早的版本會在右側增加 17px 的外邊距。這似乎是為滾動條預留的空間。當使用 position 屬性時，請始終設置 !DOCTYPE 聲明：
實例

```css
body
{
margin:0;
padding:0;
}
.container
{
position:relative;
width:100%;
}
.right
{
position:absolute;
right:0px;
width:300px;
background-color:#b0e0e6;
}
```

###使用 float 屬性來進行左和右對齊
對齊元素的另一種方法是使用 float 屬性：
實例

```css
.right
{
float:right;
width:300px;
background-color:#b0e0e6;
}
```

###跨瀏覽器兼容性問題
當像這樣對齊元素時，對 `<body>` 元素的外邊距和內邊距進行預定義是一個好主意。這樣可以避免在不同的瀏覽器中出現可見的差異。

當使用 float 屬性時，IE8 以及更早的版本存在一個問題。如果省略 !DOCTYPE 聲明，那麼 IE8 以及更早的版本會在右側增加 17px 的外邊距。這似乎是為滾動條預留的空間。當使用 float 屬性時，請始終設置 !DOCTYPE 聲明：
實例

```css
body
{
margin:0;
padding:0;
}

.right
{
float:right;
width:300px;
background-color:#b0e0e6;
}
```

___

##CSS 尺寸 (Dimension)
**CSS 尺寸 (Dimension) 屬性允許你控制元素的高度和寬度。同樣，它允許你增加行間距。**
###CSS 尺寸屬性
CSS 尺寸屬性允許你控制元素的高度和寬度。同樣，還允許你增加行間距。

屬性|	描述
:--:|:--:
height	|設置元素的高度。
line-height|	設置行高。
max-height|	設置元素的最大高度。
max-width|	設置元素的最大寬度。
min-height|	設置元素的最小高度。
min-width|	設置元素的最小寬度。
width|	設置元素的寬度。

___

##CSS 分類 (Classification)
**CSS 分類屬性允許你規定如何以及在何處顯示元素。**
###CSS 分類屬性 (Classification)
CSS 分類屬性允許你控制如何顯示元素，設置圖像顯示於另一元素中的何處，相對於其正常位置來定位元素，使用絕對值來定位元素，以及元素的可見度。

屬性|	描述
:--:|:--:
clear|	設置一個元素的側面是否允許其他的浮動元素。
cursor|	規定當指向某元素之上時顯示的指針類型。
display|	設置是否及如何顯示元素。
float|	定義元素在哪個方向浮動。
position|	把元素放置到一個靜態的、相對的、絕對的、或固定的位置中。
visibility|	設置元素是否可見或不可見。

___

##CSS 導航條
###導航欄
擁有易用的導航條對於任何網站都很重要。
通過 CSS，您能夠把乏味的 HTML 菜單轉換為漂亮的導航欄。
###導航欄 = 鏈接列表
導航欄需要標準的 HTML 作為基礎。
在我們的例子中，將用標準的 HTML 列表來構建導航欄。
導航欄基本上是一個鏈接列表，因此使用 `<ul>` 和 `<li>` 元素是非常合適的：
實例

```html
<ul>
<li><a href="default.asp">Home</a></li>
<li><a href="news.asp">News</a></li>
<li><a href="contact.asp">Contact</a></li>
<li><a href="about.asp">About</a></li>
</ul>
```

現在，讓我們從列表中去掉圓點和外邊距：
實例

```css
ul
{
list-style-type:none;
margin:0;
padding:0;
}
```

例子解釋：
* list-style-type:none - 刪除圓點。導航欄不需要列表項標記。
* 把外邊距和內邊距設置為 0 可以去除瀏覽器的默認設定。
以上例子中的代碼是用在垂直、水平導航欄中的標準代碼。

###垂直導航欄
如需構建垂直導航欄，我們只需要定義 `<a>` 元素的樣式，除了上面的代碼之外：
實例

```css
a
{
display:block;
width:60px;
}
```
例子解釋：
* display:block - 把鏈接顯示為塊元素可使整個鏈接區域可點擊（不僅僅是文本），同時也允許我們規定寬度。
* width:60px - 塊元素默認佔用全部可用寬度。我們需要規定 60 像素的寬度。

注釋：請始終規定垂直導航欄中 `<a>` 元素的寬度。如果省略寬度，IE6 會產生意想不到的結果。

###水平導航欄
有兩種創建水平導航欄的方法。使用行內或浮動列表項。
兩種方法都不錯，但是如果您希望鏈接擁有相同的尺寸，就必須使用浮動方法。

####行內列表項
除了上面的「標準」代碼，構建水平導航欄的方法之一是將 `<li>` 元素規定為行內元素：
實例

```css
li
{
display:inline;
}
```

例子解釋：
* display:inline; - 默認地，`<li>` 元素是塊元素。在這裡，我們去除了每個列表項前後的換行，以便讓它們在一行中顯示。

####對列表項進行浮動
在上面的例子中，鏈接的寬度是不同的。
為了讓所有鏈接擁有相等的寬度，浮動 `<li>` 元素並規定 `<a>` 元素的寬度：
實例

```css
li
{
float:left;
}
a
{
display:block;
width:60px;
}
```

例子解釋：
* float:left - 使用 float 來把塊元素滑向彼此。
* display:block - 把鏈接顯示為塊元素可使整個鏈接區域可點擊（不僅僅是文本），同時也允許我們規定寬度。
* width:60px - 由於塊元素默認佔用全部可用寬度，鏈接無法滑動至彼此相鄰。我們需要規定 60 像素的寬度。

___

##CSS 圖片庫
圖片庫
下面的圖片庫是由 CSS 創建的：
實例

```html
<!doctype html>
<html>
<head>
<style>
div.img
  {
  margin:3px;
  border:1px solid #bebebe;
  height:auto;
  width:auto;
  float:left;
  text-align:center;
  }
div.img img
  {
  display:inline;
  margin:3px;
  border:1px solid #bebebe;
  }
div.img a:hover img
  {
  border:1px solid #333333;
  }
div.desc
  {
  text-align:center;
  font-weight:normal;
  width:150px;
  font-size:12px;
  margin:10px 5px 10px 5px;
  }
</style>
</head>
<body>

<div class="img">
  <a target="_blank" href="/i/tulip_ballade.jpg">
  <img src="/i/tulip_ballade_s.jpg" alt="Ballade" width="160" height="160">
  </a>
  <div class="desc">在此處添加對圖像的描述</div>
</div>

<div class="img">
  <a target="_blank" href="/i/tulip_flaming_club.jpg">
  <img src="/i/tulip_flaming_club_s.jpg" alt="Ballade" width="160" height="160">
  </a>
  <div class="desc">在此處添加對圖像的描述</div>
</div>

<div class="img">
  <a target="_blank" href="/i/tulip_fringed_family.jpg">
  <img src="/i/tulip_fringed_family_s.jpg" alt="Ballade" width="160" height="160">
  </a>
  <div class="desc">在此處添加對圖像的描述</div>
</div>

<div class="img">
  <a target="_blank" href="/i/tulip_peach_blossom.jpg">
  <img src="/i/tulip_peach_blossom_s.jpg" alt="Ballade" width="160" height="160">
  </a>
  <div class="desc">在此處添加對圖像的描述</div>
</div>

</body>
</html>
```

___

##CSS 圖像透明度
通過 CSS 創建透明圖像是很容易的。
注釋：CSS opacity 屬性是 W3C CSS 推薦標準的一部分。

###實例 1 - 創建透明圖像
定義透明效果的 CSS3 屬性是 opacity。
首先，我們將展示如何通過 CSS 來創建透明圖像。
常規圖像：
![Peach Blossom](/assets/tulippeachblossom.jpg)
帶有透明度的相同圖像：
`<img sryc="/assets/tulippeachblossom.jpg">`

請看下面的 CSS：

```css
img
{
opacity:0.4;
filter:alpha(opacity=40); /* 針對 IE8 以及更早的版本 */
}
```

IE9, Firefox, Chrome, Opera 和 Safari 使用屬性 opacity 來設定透明度。opacity 屬性能夠設置的值從 0.0 到 1.0。值越小，越透明。
IE8 以及更早的版本使用濾鏡 filter:alpha(opacity=x)。x 能夠取的值從 0 到 100。值越小，越透明。

###實例 2 - 圖像透明度 - Hover 效果

CSS 是這樣的：

```css
img
{
opacity:0.4;
filter:alpha(opacity=40); /* 針對 IE8 以及更早的版本 */
}
img:hover
{
opacity:1.0;
filter:alpha(opacity=100); /* 針對 IE8 以及更早的版本 */
}
```

第一個 CSS 代碼塊類似實例 1 中的代碼。此外，我們已經設置了當鼠標指針位於圖像上時的樣式。在這個例子中，當指針移動到圖像上時，我們希望圖像是不透明的。

對應的 CSS 是：opacity=1。

IE8 以及更早的瀏覽器：filter:alpha(opacity=100)。
當鼠標指針移出圖像後，圖像會再次透明。

###實例 3 - 透明框中的文本

源代碼是這樣的：

```html
<!DOCTYPE html>
<html>
<head>
<style>
div.background
{
  width: 400px;
  height: 266px;
  background: url('/i/tulip_peach_blossom_w.jpg') no-repeat;
  border: 1px solid black;
}

div.transbox
{
  width: 338px;
  height: 204px;
  margin:30px;
  background-color: #ffffff;
  border: 1px solid black;
  /* for IE */
  filter:alpha(opacity=60);
  /* CSS3 standard */
  opacity:0.6;
}

div.transbox p
{
  margin: 30px 40px;
}
</style>
</head>

<body>

<div class="background">
<div class="transbox">
<p>
This is some text that is placed in the transparent box.
This is some text that is placed in the transparent box.
This is some text that is placed in the transparent box.
This is some text that is placed in the transparent box.
This is some text that is placed in the transparent box.
</p>
</div>
</div>

</body>
</html>
```

首先，我們創建一個 div 元素 (class="background")，它有固定的高度和寬度、背景圖像，以及邊框。然後我們在第一個 div 內創建稍小的 div (class="transbox")。"transbox" div 有固定的寬度、背景色和邊框 - 並且它是透明的。在透明 div 內部，我們在 p 元素中加入了一些文本。

___

##CSS2 媒介類型
**媒介類型(Media Types)允許你定義以何種媒介來提交文檔。文檔可以被顯示在顯示器、紙媒介或者聽覺瀏覽器等等。**
###媒介類型
某些 CSS 屬性僅僅被設計為針對某些媒介。比方說 "voice-family" 屬性被設計為針對聽覺用戶終端。其他的屬性可被用於不同的媒介。例如，"font-size" 屬性可被用於顯示器以及印刷媒介，但是也許會帶有不同的值。顯示器上面的顯示的文檔通常會需要比紙媒介文檔更大的字號，同時，在顯示器上，sans-serif 字體更易閱讀，而在紙媒介上，serif 字體更易閱讀。

###@media規則
@media 規則使你有能力在相同的樣式表中，使用不同的樣式規則來針對不同的媒介。

下面這個例子中的樣式告知瀏覽器在顯示器上顯示 14 像素的 Verdana 字體。但是假如頁面需要被打印，將使用 10 個像素的 Times 字體。注意：font-weight 被設置為粗體，不論顯示器還是紙媒介：

```html
<html>
<head>

<style>
@media screen
{
p.test {font-family:verdana,sans-serif; font-size:14px}
}

@media print
{
p.test {font-family:times,serif; font-size:10px}
}

@media screen,print
{
p.test {font-weight:bold}
}
</style>

</head>

<body>....</body>

</html>
```

不同的媒介類型
注釋：媒介類型名稱對大小寫不敏感。

媒介類型|	描述
:--:|:--:
all|	用於所有的媒介設備。
aural|	用於語音和音頻合成器。
braille|	用於盲人用點字法觸覺回饋設備。
embossed|	用於分頁的盲人用點字法打印機。
handheld|	用於小的手持的設備。
print|	用於打印機。
projection|	用於方案展示，比如幻燈片。
screen|	用於電腦顯示器。
tty|	用於使用固定密度字母柵格的媒介，比如電傳打字機和終端。
tv|	用於電視機類型的設備。

___

##CSS 注意事項
**本節列出了在使用 CSS 時盡量避免使用的技術。**
###Internet Explorer Behaviors
它是什麼？Internet Explorer 5 引入了行為 (behaviors)。behaviors 是一種通過使用 CSS 向 HTML 元素添加行為的方法。
為什麼要避免它？只有 Internet Explorer 支持 behavior 屬性。
用什麼代替？請使用 JavaScript 和 HTML DOM 取而代之。

###例子 1 - Mouseover Highlight
下面的 HTML 文件中有一個 `<style>` 元素，它為 `<h1>` 元素定義了一個行為：

```html
<html>
<head>
<style type="text/css">
h1 { behavior: url(behave.htc) }
</style>
</head>

<body>
<h1>Mouse over me!!!</h1>
</body>
</html>
```

下面是 XML 文檔 "behave.htc"：

```xml
<attach for="element" event="onmouseover" handler="hig_lite" />
<attach for="element" event="onmouseout" handler="low_lite" />

<script type="text/javascript">
function hig_lite()
{
element.style.color='red';
}

function low_lite()
{
element.style.color='blue';
}
</script>
```

behavior 文件包含了針對元素的 JavaScript 和 事件句柄。

###例子 2 - Typewriter Simulation
下面的 HTML 文件中有一個 `<style>` 元素，它為 id 為 "typing" 的元素定義了一個行為：

```html
<html>
<head>
<style type="text/css">
#typing
{
behavior:url(behave_typing.htc);
font-family:'courier new';
}
</style>
</head>

<body>
<span id="typing" speed="100">IE5 introduced DHTML behaviors.
Behaviors are a way to add DHTML functionality to HTML elements
with the ease of CSS.<br /><br />How do behaviors work?<br />
By using XML we can link behaviors to any element in a web page
and manipulate that element.</p>
</span>
</body>
</html>
```

下面是 XML 文檔 "behave.htc"：

```xml
<attach for="window" event="onload" handler="beginTyping" />
<method name="type" />

<script type="text/javascript">
var i,text1,text2,textLength,t;

function beginTyping()
{
i=0;
text1=element.innerText;
textLength=text1.length;
element.innerText="";
text2="";
t=window.setInterval(element.id+".type()",speed);
}

function type()
{
text2=text2+text1.substring(i,i+1);
element.innerText=text2;
i=i+1;
if (i==textLength)
  {
  clearInterval(t);
  }
}
</script>
```

___

