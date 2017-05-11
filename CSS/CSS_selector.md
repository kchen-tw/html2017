#CSS 選擇器
##CSS 元素選擇器
最常見的 CSS 選擇器是元素選擇器。換句話說，文檔的元素就是最基本的選擇器。
如果設置 HTML 的樣式，選擇器通常將是某個 HTML 元素，比如 p、h1、em、a，甚至可以是 html 本身：

```css
html {color:black;}
h1 {color:blue;}
h2 {color:silver;}
```

可以將某個樣式從一個元素切換到另一個元素。
假設您決定將上面的段落文本（而不是 h1 元素）設置為灰色。只需要把 h1 選擇器改為 

```css
p：
html {color:black;}
p {color:gray;}
h2 {color:silver;}
```

###類型選擇器
在 W3C 標準中，元素選擇器又稱為類型選擇器（type selector）。
「類型選擇器匹配文檔語言元素類型的名稱。類型選擇器匹配文檔樹中該元素類型的每一個實例。」
下面的規則匹配文檔樹中所有 h1 元素：

```css
h1 {font-family: sans-serif;}
```

因此，我們也可以為 XML 文檔中的元素設置樣式：
XML 文檔：

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

CSS 文檔：

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
##CSS 分組
###選擇器分組
假設希望 h2 元素和段落都有灰色。為達到這個目的，最容易的做法是使用以下聲明：

```css
h2, p {color:gray;}
```

將 h2 和 p 選擇器放在規則左邊，然後用逗號分隔，就定義了一個規則。其右邊的樣式（color:gray;）將應用到這兩個選擇器所引用的元素。逗號告訴瀏覽器，規則中包含兩個不同的選擇器。如果沒有這個逗號，那麼規則的含義將完全不同。參見後代選擇器。

可以將任意多個選擇器分組在一起，對此沒有任何限制。
例如，如果您想把很多元素顯示為灰色，可以使用類似如下的規則：

```css
body, h2, p, table, th, td, pre, strong, em {color:gray;}
```

提示：通過分組，創作者可以將某些類型的樣式「壓縮」在一起，這樣就可以得到更簡潔的樣式表。

以下的兩組規則能得到同樣的結果，不過可以很清楚地看出哪一個寫起來更容易：

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

分組提供了一些有意思的選擇。例如，下例中的所有規則分組都是等價的，每個組只是展示了對選擇器和聲明分組的不同方法：

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

請注意，group 3 中使用了「聲明分組」。稍後我們會為您介紹「聲明分組」。

###通配符選擇器
CSS2 引入了一種新的簡單選擇器 - 通配選擇器（universal selector），顯示為一個星號（*）。該選擇器可以與任何元素匹配，就像是一個通配符。

例如，下面的規則可以使文檔中的每個元素都為紅色：
```
* {color:red;}
```

這個聲明等價於列出了文檔中所有元素的一個分組選擇器。利用通配選擇器，只需敲一次鍵（僅一個星號）就能使文檔中所有元素的 color 屬性值指定為 red。

###聲明分組
我們既可以對選擇器進行分組，也可以對聲明分組。

假設您希望所有 h1 元素都有紅色背景，並使用 28 像素高的 Verdana 字體顯示為藍色文本，可以寫以下樣式：

```css
h1 {font: 28px Verdana;}
h1 {color: blue;}
h1 {background: red;}
```

但是上面這種做法的效率並不高。尤其是當我們為一個有多個樣式的元素創建這樣一個列表時會很麻煩。相反，我們可以將聲明分組在一起：

```css
h1 {font: 28px Verdana; color: white; background: black;}
```

這與前面的 3 行樣式表的效果完全相同。

注意，對聲明分組，一定要在各個聲明的最後使用分號，這很重要。瀏覽器會忽略樣式表中的空白符。只要加了分號，就可以毫無顧忌地採用以下格式建立樣式：

```css
h1 {
  font: 28px Verdana;
  color: blue;
  background: red;
  }
```

怎麼樣，上面這種寫法的可讀性是不是更強。
不過，如果忽略了第二個分號，用戶代理就會把這個樣式表解釋如下：

```css
h1 {
  font: 28px Verdana;
  color: blue background: red;
  }
```

因為 background 對 color 來說不是一個合法值，而且由於只能為 color 指定一個關鍵字，所以用戶代理會完全忽略這個 color 聲明（包括 background: black 部分）。這樣 h1 標題只會顯示為藍色，而沒有紅色背景，不過更有可能根本得不到藍色的 h1。相反，這些標題只會顯示為默認顏色（通常是黑色），而且根本沒有背景色。font: 28px Verdana 聲明仍能正常發揮作用，因為它確實正確地以一個分號結尾。

與選擇器分組一樣，聲明分組也是一種便利的方法，可以縮短樣式表，使之更清晰，也更易維護。

提示：在規則的最後一個聲明後也加上分號是一個好習慣。在向規則增加另一個聲明時，就不必擔心忘記再插入一個分號。
結合選擇器和聲明的分組
我們可以在一個規則中結合選擇器分組和聲明分組，就可以使用很少的語句定義相對複雜的樣式。
下面的規則為所有標題指定了一種複雜的樣式：

```css
h1, h2, h3, h4, h5, h6 {
  color:gray;
  background: white;
  padding: 10px;
  border: 1px solid black;
  font-family: Verdana;
  }
```

上面這條規則將所有標題的樣式定義為帶有白色背景的灰色文本，其內邊距是 10 像素，並帶有 1 像素的實心邊框，文本字體是 Verdana。

___

##CSS 類選擇器詳解
**類選擇器允許以一種獨立於文檔元素的方式來指定樣式。**
###CSS 類選擇器
類選擇器允許以一種獨立於文檔元素的方式來指定樣式。
該選擇器可以單獨使用，也可以與其他元素結合使用。

提示：只有適當地標記文檔後，才能使用這些選擇器，所以使用這兩種選擇器通常需要先做一些構想和計劃。

要應用樣式而不考慮具體設計的元素，最常用的方法就是使用類選擇器。

####修改 HTML 代碼
在使用類選擇器之前，需要修改具體的文檔標記，以便類選擇器正常工作。

為了將類選擇器的樣式與元素關聯，必須將 class 指定為一個適當的值。請看下面的 HTML 代碼：

```html
<h1 class="important">
This heading is very important.
</h1>

<p class="important">
This paragraph is very important.
</p>
```

在上面的代碼中，兩個元素的 class 都指定為 important：第一個標題（ h1 元素），第二個段落（p 元素）。

#####語法
然後我們使用以下語法向這些歸類的元素應用樣式，即類名前有一個點號（.），然後結合通配選擇器：

```css
*.important {color:red;}
```

如果您只想選擇所有類名相同的元素，可以在類選擇器中忽略通配選擇器，這沒有任何不好的影響：

```css
.important {color:red;}
```

####結合元素選擇器
類選擇器可以結合元素選擇器來使用。
例如，您可能希望只有段落顯示為紅色文本：

```css
p.important {color:red;}
```

選擇器現在會匹配 class 屬性包含 important 的所有 p 元素，但是其他任何類型的元素都不匹配，不論是否有此 class 屬性。選擇器 p.important 解釋為：「其 class 屬性值為 important 的所有段落」。 因為 h1 元素不是段落，這個規則的選擇器與之不匹配，因此 h1 元素不會變成紅色文本。

如果你確實希望為 h1 元素指定不同的樣式，可以使用選擇器 h1.important：

```css
p.important {color:red;}
h1.important {color:blue;}
```

###CSS 多類選擇器
在上一節中，我們處理了 class 值中包含一個詞的情況。在 HTML 中，一個 class 值中可能包含一個詞列表，各個詞之間用空格分隔。例如，如果希望將一個特定的元素同時標記為重要（important）和警告（warning），就可以寫作：

```html
<p class="important warning">
This paragraph is a very important warning.
</p>
```

這兩個詞的順序無關緊要，寫成 warning important 也可以。

我們假設 class 為 important 的所有元素都是粗體，而 class 為 warning 的所有元素為斜體，class 中同時包含 important 和 warning 的所有元素還有一個銀色的背景 。就可以寫作：

```css
.important {font-weight:bold;}
.warning {font-style:italic;}
.important.warning {background:silver;}
```

通過把兩個類選擇器鏈接在一起，僅可以選擇同時包含這些類名的元素（類名的順序不限）。
如果一個多類選擇器包含類名列表中沒有的一個類名，匹配就會失敗。請看下面的規則：

```css
.important.urgent {background:silver;}
```

不出所料，這個選擇器將只匹配 class 屬性中包含詞 important 和 urgent 的 p 元素。因此，如果一個 p 元素的 class 屬性中只有詞 important 和 warning，將不能匹配。不過，它能匹配以下元素：

```html
<p class="important urgent warning">
This paragraph is a very important and urgent warning.
</p>
```

重要事項：在 IE7 之前的版本中，不同平台的 Internet Explorer 都不能正確地處理多類選擇器。

___

##CSS ID 選擇器詳解
**ID 選擇器允許以一種獨立於文檔元素的方式來指定樣式。**
###CSS ID 選擇器
在某些方面，ID 選擇器類似於類選擇器，不過也有一些重要差別。

####語法
首先，ID 選擇器前面有一個 # 號 - 也稱為棋盤號或井號。
請看下面的規則：

```css
*#intro {font-weight:bold;}
```

與類選擇器一樣，ID 選擇器中可以忽略通配選擇器。前面的例子也可以寫作：

```css
#intro {font-weight:bold;}
```

這個選擇器的效果將是一樣的。
第二個區別是 ID 選擇器不引用 class 屬性的值，毫無疑問，它要引用 id 屬性中的值。
以下是一個實際 ID 選擇器的例子：

```html
<p id="intro">This is a paragraph of introduction.</p>
```

###類選擇器還是 ID 選擇器？
在類選擇器這一章中我們曾講解過，可以為任意多個元素指定類。前一章中類名 important 被應用到 p 和 h1 元素，而且它還可以應用到更多元素。

區別 1：只能在文檔中使用一次

與類不同，在一個 HTML 文檔中，ID 選擇器會使用一次，而且僅一次。

區別 2：不能使用 ID 詞列表

不同於類選擇器，ID 選擇器不能結合使用，因為 ID 屬性不允許有以空格分隔的詞列表。

區別 3：ID 能包含更多含義

類似於類，可以獨立於元素來選擇 ID。有些情況下，您知道文檔中會出現某個特定 ID 值，但是並不知道它會出現在哪個元素上，所以您想聲明獨立的 ID 選擇器。例如，您可能知道在一個給定的文檔中會有一個 ID 值為 mostImportant 的元素。您不知道這個最重要的東西是一個段落、一個短語、一個列表項還是一個小節標題。您只知道每個文檔都會有這麼一個最重要的內容，它可能在任何元素中，而且只能出現一個。在這種情況下，可以編寫如下規則：

```css
#mostImportant {color:red; background:yellow;}
```

這個規則會與以下各個元素匹配（這些元素不能在同一個文檔中同時出現，因為它們都有相同的 ID 值）：

```html
<h1 id="mostImportant">This is important!</h1>
<em id="mostImportant">This is important!</em>
<ul id="mostImportant">This is important!</ul>
```

###區分大小寫
請注意，類選擇器和 ID 選擇器可能是區分大小寫的。這取決於文檔的語言。HTML 和 XHTML 將類和 ID 值定義為區分大小寫，所以類和 ID 值的大小寫必須與文檔中的相應值匹配。
因此，對於以下的 CSS 和 HTML，元素不會變成粗體：

```html
#intro {font-weight:bold;}

<p id="Intro">This is a paragraph of introduction.</p>
```

由於字母 i 的大小寫不同，所以選擇器不會匹配上面的元素。
___

##CSS 屬性選擇器詳解
**CSS 2 引入了屬性選擇器。**
**屬性選擇器可以根據元素的屬性及屬性值來選擇元素。**
###簡單屬性選擇
如果希望選擇有某個屬性的元素，而不論屬性值是什麼，可以使用簡單屬性選擇器。

例子 1
如果您希望把包含標題（title）的所有元素變為紅色，可以寫作：

```css
*[title] {color:red;}
```

例子 2
與上面類似，可以只對有 href 屬性的錨（a 元素）應用樣式：

```css
a[href] {color:red;}
```

例子 3
還可以根據多個屬性進行選擇，只需將屬性選擇器鏈接在一起即可。
例如，為了將同時有 href 和 title 屬性的 HTML 超鏈接的文本設置為紅色，可以這樣寫：

```css
a[href][title] {color:red;}
```

例子 4
可以採用一些創造性的方法使用這個特性。
例如，可以對所有帶有 alt 屬性的圖像應用樣式，從而突出顯示這些有效的圖像：

```css
img[alt] {border: 5px solid red;}
```

提示：上面這個特例更適合用來診斷而不是設計，即用來確定圖像是否確實有效。

例子 5：為 XML 文檔使用屬性選擇器

屬性選擇器在 XML 文檔中相當有用，因為 XML 語言主張要針對元素和屬性的用途指定元
素名和屬性名。

假設我們為描述太陽系行星設計了一個 XML 文檔。如果我們想選擇有 moons 屬性的所有 planet 元素，使之顯示為紅色，以便能更關注有 moons 的行星，就可以這樣寫：

```css
planet[moons] {color:red;}
```
這會讓以下標記片段中的第二個和第三個元素的文本顯示為紅色，但第一個元素的文本不是紅色：

```html
<planet>Venus</planet>
<planet moons="1">Earth</planet>
<planet moons="2">Mars</planet>
```

###根據具體屬性值選擇
除了選擇擁有某些屬性的元素，還可以進一步縮小選擇範圍，只選擇有特定屬性值的元素。

例子 1
例如，假設希望將指向 Web 服務器上某個指定文檔的超鏈接變成紅色，可以這樣寫：

```css
a[href="http://www.w3school.com.cn/about_us.asp"] {color: red;}
```

例子 2
與簡單屬性選擇器類似，可以把多個屬性-值選擇器鏈接在一起來選擇一個文檔。

```css
a[href="http://www.w3school.com.cn/"][title="W3School"] {color: red;}
```

這會把以下標記中的第一個超鏈接的文本變為紅色，但是第二個或第三個鏈接不受影響：

```html
<a href="http://www.w3school.com.cn/" title="W3School">W3School</a>
<a href="http://www.w3school.com.cn/css/" title="CSS">CSS</a>
<a href="http://www.w3school.com.cn/html/" title="HTML">HTML</a>
```

例子 3
同樣地，XML 語言也可以利用這種方法來設置樣式。
下面我們再回到行星那個例子中。假設只希望選擇 moons 屬性值為 1 的那些 planet 元素：

```css
planet[moons="1"] {color: red;}
```

上面的代碼會把以下標記中的第二個元素變成紅色，但第一個和第三個元素不受影響：

```html
<planet>Venus</planet>
<planet moons="1">Earth</planet>
<planet moons="2">Mars</planet>
```

屬性與屬性值必須完全匹配
請注意，這種格式要求必須與屬性值完全匹配。

如果屬性值包含用空格分隔的值列表，匹配就可能出問題。
請考慮一下的標記片段：

```html
<p class="important warning">This paragraph is a very important warning.</p>
```

如果寫成 p[class="important"]，那麼這個規則不能匹配示例標記。
要根據具體屬性值來選擇該元素，必須這樣寫：

```css
p[class="important warning"] {color: red;}
```

####根據部分屬性值選擇
如果需要根據屬性值中的詞列表的某個詞進行選擇，則需要使用波浪號（~）。
假設您想選擇 class 屬性中包含 important 的元素，可以用下面這個選擇器做到這一點：

```css
p[class~="important"] {color: red;}
```

如果忽略了波浪號，則說明需要完成完全值匹配。

#####部分值屬性選擇器與點號類名記法的區別
該選擇器等價於我們在類選擇器中討論過的點號類名記法。
也就是說，p.important 和 p[class="important"] 應用到 HTML 文檔時是等價的。

那麼，為什麼還要有 "~=" 屬性選擇器呢？因為它能用於任何屬性，而不只是 class。
例如，可以有一個包含大量圖像的文檔，其中只有一部分是圖片。對此，可以使用一個基於 title 文檔的部分屬性選擇器，只選擇這些圖片：

```css
img[title~="Figure"] {border: 1px solid gray;}
```

這個規則會選擇 title 文本包含 "Figure" 的所有圖像。沒有 title 屬性或者 title 屬性中不包含 "Figure" 的圖像都不會匹配。

#####子串匹配屬性選擇器
下面為您介紹一個更高級的選擇器模塊，它是 CSS2 完成之後發佈的，其中包含了更多的部分值屬性選擇器。按照規範的說法，應該稱之為「子串匹配屬性選擇器」。

很多現代瀏覽器都支持這些選擇器，包括 IE7。

下表是對這些選擇器的簡單總結：

類型|	描述
:--:|:--:
[abc^="def"]|	選擇 abc 屬性值以 "def" 開頭的所有元素
[abc$="def"]|	選擇 abc 屬性值以 "def" 結尾的所有元素
[abc*="def"]|	選擇 abc 屬性值中包含子串 "def" 的所有元素

可以想到，這些選擇有很多用途。

舉例來說，如果希望對指向 W3School 的所有鏈接應用樣式，不必為所有這些鏈接指定 class，再根據這個類編寫樣式，而只需編寫以下規則：

```css
a[href*="w3school.com.cn"] {color: red;}
```

提示：任何屬性都可以使用這些選擇器。

####特定屬性選擇類型
最後為您介紹特定屬性選擇器。請看下面的例子：

```css
*[lang|="en"] {color: red;}
```

上面這個規則會選擇 lang 屬性等於 en 或以 en- 開頭的所有元素。因此，以下示例標記中的前三個元素將被選中，而不會選擇後兩個元素：

```html
<p lang="en">Hello!</p>
<p lang="en-us">Greetings!</p>
<p lang="en-au">G'day!</p>
<p lang="fr">Bonjour!</p>
<p lang="cy-en">Jrooana!</p>
```

一般來說，[att|="val"] 可以用於任何屬性及其值。
假設一個 HTML 文檔中有一系列圖片，其中每個圖片的文件名都形如 figure-1.jpg 和 figure-2.jpg。就可以使用以下選擇器匹配所有這些圖像：

```css
img[src|="figure"] {border: 1px solid gray;}
```

當然，這種屬性選擇器最常見的用途還是匹配語言值。

###CSS 選擇器參考手冊
選擇器|	描述
:--:|:--:
[attribute]|	用於選取帶有指定屬性的元素。
[attribute=value]|	用於選取帶有指定屬性和值的元素。
[attribute~=value]|	用於選取屬性值中包含指定詞彙的元素。
[attribute\|=value]|	用於選取帶有以指定值開頭的屬性值的元素，該值必須是整個單詞。
[attribute^=value]|	匹配屬性值以指定值開頭的每個元素。
[attribute$=value]|	匹配屬性值以指定值結尾的每個元素。
[attribute*=value]|	匹配屬性值中包含指定值的每個元素。

___