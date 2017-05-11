#CSS背景
**CSS 允許應用純色作為背景，也允許使用背景圖像創建相當複雜的效果。
CSS 在這方面的能力遠遠在 HTML 之上。**
##背景色
可以使用 background-color 屬性為元素設置背景色。這個屬性接受任何合法的顏色值。
這條規則把元素的背景設置為灰色：
`p {background-color: gray;}`
如果您希望背景色從元素中的文本向外少有延伸，只需增加一些內邊距：
`p {background-color: gray; padding: 20px;}`

可以為所有元素設置背景色，這包括 body 一直到 em 和 a 等行內元素。

background-color 不能繼承，其默認值是 transparent。transparent 有「透明」之意。也就是說，如果一個元素沒有指定背景色，那麼背景就是透明的，這樣其祖先元素的背景才能可見。

##背景圖像
要把圖像放入背景，需要使用 background-image 屬性。background-image 屬性的默認值是 none，表示背景上沒有放置任何圖像。

如果需要設置一個背景圖像，必須為這個屬性設置一個 URL 值：
`body {background-image: url(/i/eg_bg_04.gif);}`
大多數背景都應用到 body 元素，不過並不僅限於此。
下面例子為一個段落應用了一個背景，而不會對文檔的其他部分應用背景：
`p.flower {background-image: url(/i/eg_bg_03.gif);}`
您甚至可以為行內元素設置背景圖像，下面的例子為一個鏈接設置了背景圖像：
`a.radio {background-image: url(/i/eg_bg_07.gif);}`

理論上講，甚至可以向 textareas 和 select 等替換元素的背景應用圖像，不過並不是所有用戶代理都能很好地處理這種情況。
另外還要補充一點，background-image 也不能繼承。事實上，所有背景屬性都不能繼承。

##背景重復
如果需要在頁面上對背景圖像進行平鋪，可以使用 background-repeat 屬性。

屬性值 repeat 導致圖像在水平垂直方向上都平鋪，就像以往背景圖像的通常做法一樣。repeat-x 和 repeat-y 分別導致圖像只在水平或垂直方向上重復，no-repeat 則不允許圖像在任何方向上平鋪。

默認地，背景圖像將從一個元素的左上角開始。請看下面的例子：

```css
body
  { 
  background-image: url(/i/eg_bg_03.gif);
  background-repeat: repeat-y;
  }
```

##背景定位
可以利用 background-position 屬性改變圖像在背景中的位置。
下面的例子在 body 元素中將一個背景圖像居中放置：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:center;
  }
```
為 background-position 屬性提供值有很多方法。首先，可以使用一些關鍵字：top、bottom、left、right 和 center。通常，這些關鍵字會成對出現，不過也不總是這樣。還可以使用長度值，如 100px 或 5cm，最後也可以使用百分數值。不同類型的值對於背景圖像的放置稍有差異。

關鍵字
圖像放置關鍵字最容易理解，其作用如其名稱所表明的。例如，top right 使圖像放置在元素內邊距區的右上角。
根據規範，位置關鍵字可以按任何順序出現，只要保證不超過兩個關鍵字 - 一個對應水平方向，另一個對應垂直方向。
如果只出現一個關鍵字，則認為另一個關鍵字是 center。
所以，如果希望每個段落的中部上方出現一個圖像，只需聲明如下：

```css
p
  { 
    background-image:url('bgimg.gif');
    background-repeat:no-repeat;
    background-position:top;
  }
```

下面是等價的位置關鍵字：

單一關鍵字|	等價的關鍵字
:--:|:--:
center|	center center
top	|top center 或 center top
bottom	|bottom center 或 center bottom
right	|right center 或 center right
left	|left center 或 center left

百分數值
百分數值的表現方式更為複雜。假設你希望用百分數值將圖像在其元素中居中，這很容易：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50% 50%;
  }
```
這會導致圖像適當放置，其中心與其元素的中心對齊。換句話說，百分數值同時應用於元素和圖像。也就是說，圖像中描述為 50% 50% 的點（中心點）與元素中描述為 50% 50% 的點（中心點）對齊。

如果圖像位於 0% 0%，其左上角將放在元素內邊距區的左上角。如果圖像位置是 100% 100%，會使圖像的右下角放在右邊距的右下角。

因此，如果你想把一個圖像放在水平方向 2/3、垂直方向 1/3 處，可以這樣聲明：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:66% 33%;
  }
```
如果只提供一個百分數值，所提供的這個值將用作水平值，垂直值將假設為 50%。這一點與關鍵字類似。

background-position 的默認值是 0% 0%，在功能上相當於 top left。這就解釋了背景圖像為什麼總是從元素內邊距區的左上角開始平鋪，除非您設置了不同的位置值。

長度值
長度值解釋的是元素內邊距區左上角的偏移。偏移點是圖像的左上角。
比如，如果設置值為 50px 100px，圖像的左上角將在元素內邊距區左上角向右 50 像素、向下 100 像素的位置上：

```css
body
  { 
    background-image:url('/i/eg_bg_03.gif');
    background-repeat:no-repeat;
    background-position:50px 100px;
  }
```
注意，這一點與百分數值不同，因為偏移只是從一個左上角到另一個左上角。也就是說，圖像的左上角與 background-position 聲明中的指定的點對齊。

##背景關聯
如果文檔比較長，那麼當文檔向下滾動時，背景圖像也會隨之滾動。當文檔滾動到超過圖像的位置時，圖像就會消失。
您可以通過 background-attachment 屬性防止這種滾動。通過這個屬性，可以聲明圖像相對於可視區是固定的（fixed），因此不會受到滾動的影響：

```css
body 
  {
    background-image:url(/i/eg_bg_02.gif);
    background-repeat:no-repeat;
    background-attachment:fixed
  }
```

background-attachment 屬性的默認值是 scroll，也就是說，在默認的情況下，背景會隨文檔滾動。

##CSS 背景屬性

屬性|	描述
:--:|:--:
background|	簡寫屬性，作用是將背景屬性設置在一個聲明中。
background-attachment|	背景圖像是否固定或者隨著頁面的其餘部分滾動。
background-color	|設置元素的背景顏色。
background-image	|把圖像設置為背景。
background-position	|設置背景圖像的起始位置。
background-repeat	|設置背景圖像是否及如何重復。
___

#CSS文本
**CSS 文本屬性可定義文本的外觀。
通過文本屬性，您可以改變文本的顏色、字符間距，對齊文本，裝飾文本，對文本進行縮進，等等。**
##縮進文本
把 Web 頁面上的段落的第一行縮進，這是一種最常用的文本格式化效果。
CSS 提供了 text-indent 屬性，該屬性可以方便地實現文本縮進。

通過使用 text-indent 屬性，所有元素的第一行都可以縮進一個給定的長度，甚至該長度可以是負值。
這個屬性最常見的用途是將段落的首行縮進，下面的規則會使所有段落的首行縮進 5 em：
`p {text-indent: 5em;}`

注意：一般來說，可以為所有塊級元素應用 text-indent，但無法將該屬性應用於行內元素，圖像之類的替換元素上也無法應用 text-indent 屬性。不過，如果一個塊級元素（比如段落）的首行中有一個圖像，它會隨該行的其餘文本移動。
提示：如果想把一個行內元素的第一行「縮進」，可以用左內邊距或外邊距創造這種效果。

使用負值
text-indent 還可以設置為負值。利用這種技術，可以實現很多有趣的效果，比如「懸掛縮進」，即第一行懸掛在元素中余下部分的左邊：
`p {text-indent: -5em;}`
不過在為 text-indent 設置負值時要當心，如果對一個段落設置了負值，那麼首行的某些文本可能會超出瀏覽器窗口的左邊界。為了避免出現這種顯示問題，建議針對負縮進再設置一個外邊距或一些內邊距：
`p {text-indent: -5em; padding-left: 5em;}`

使用百分比值
text-indent 可以使用所有長度單位，包括百分比值。
百分數要相對於縮進元素父元素的寬度。換句話說，如果將縮進值設置為 20%，所影響元素的第一行會縮進其父元素寬度的 20%。
在下例中，縮進值是父元素的 20%，即 100 個像素：

```html
div {width: 500px;}
p {text-indent: 20%;}

<div>
<p>this is a paragragh</p>
</div>
```

繼承
text-indent 屬性可以繼承，請考慮如下標記：

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

以上標記中的段落也會縮進 50 像素，這是因為這個段落繼承了 id 為 inner 的 div 元素的縮進值。

##水平對齊
text-align 是一個基本的屬性，它會影響一個元素中的文本行互相之間的對齊方式。它的前 3 個值相當直接，不過第 4 個和第 5 個則略有些複雜。

值 left、right 和 center 會導致元素中的文本分別左對齊、右對齊和居中。

西方語言都是從左向右讀，所有 text-align 的默認值是 left。文本在左邊界對齊，右邊界呈鋸齒狀（稱為「從左到右」文本）。對於希伯來語和阿拉伯語之類的的語言，text-align 則默認為 right，因為這些語言從右向左讀。不出所料，center 會使每個文本行在元素中居中。

提示：將塊級元素或表元素居中，要通過在這些元素上適當地設置左、右外邊距來實現。

##text-align:center 與 `<CENTER>`
您可能會認為 text-align:center 與 `<CENTER>` 元素的作用一樣，但實際上二者大不相同。
`<CENTER>` 不僅影響文本，還會把整個元素居中。text-align 不會控制元素的對齊，而只影響內部內容。元素本身不會從一段移到另一端，只是其中的文本受影響。

##justify
最後一個水平對齊屬性是 justify。

在兩端對齊文本中，文本行的左右兩端都放在父元素的內邊界上。然後，調整單詞和字母間的間隔，使各行的長度恰好相
等。您也許已經注意到了，兩端對齊文本在打印領域很常見。

需要注意的是，要由用戶代理（而不是 CSS）來確定兩端對齊文本如何拉伸，以填滿父元素左右邊界之間的空間。如需瞭解詳情，請參閱 CSS text-align 屬性參考頁。

##字間隔
word-spacing 屬性可以改變字（單詞）之間的標準間隔。其默認值 normal 與設置值為 0 是一樣的。

word-spacing 屬性接受一個正長度值或負長度值。如果提供一個正長度值，那麼字之間的間隔就會增加。為 word-spacing 設置一個負值，會把它拉近：

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

注釋：如需深入理解 CSS 對「字」（word）的定義，請訪問 CSS word-spacing 屬性參考頁。

##字母間隔
letter-spacing 屬性與 word-spacing 的區別在於，字母間隔修改的是字符或字母之間的間隔。

與 word-spacing 屬性一樣，letter-spacing 屬性的可取值包括所有長度。默認關鍵字是 normal（這與 letter-spacing:0 相同）。輸入的長度值會使字母之間的間隔增加或減少指定的量：

```html
h1 {letter-spacing: -0.5em}
h4 {letter-spacing: 20px}

<h1>This is header 1</h1>
<h4>This is header 4</h4>
```

##字符轉換
text-transform 屬性處理文本的大小寫。這個屬性有 4 個值：
* none
* uppercase
* lowercase
* capitalize
默認值 none 對文本不做任何改動，將使用源文檔中的原有大小寫。顧名思義，uppercase 和 lowercase 將文本轉換為全大寫和全小寫字符。最後，capitalize 只對每個單詞的首字母大寫。

作為一個屬性，text-transform 可能無關緊要，不過如果您突然決定把所有 h1 元素變為大寫，這個屬性就很有用。不必單獨地修改所有 h1 元素的內容，只需使用 text-transform 為你完成這個修改：
`h1 {text-transform: uppercase}`
使用 text-transform 有兩方面的好處。首先，只需寫一個簡單的規則來完成這個修改，而無需修改 h1 元素本身。其次，如果您以後決定將所有大小寫再切換為原來的大小寫，可以更容易地完成修改。

##文本裝飾
接下來，我們討論 text-decoration 屬性，這是一個很有意思的屬性，它提供了很多非常有趣的行為。

text-decoration 有 5 個值：
* none
* underline
* overline
* line-through
* blink

不出所料，underline 會對元素加下划線，就像 HTML 中的 U 元素一樣。overline 的作用恰好相反，會在文本的頂端畫一個上划線。值 line-through 則在文本中間畫一個貫穿線，等價於 HTML 中的 S 和 strike 元素。blink 會讓文本閃爍，類似於 Netscape 支持的頗招非議的 blink 標記。

none 值會關閉原本應用到一個元素上的所有裝飾。通常，無裝飾的文本是默認外觀，但也不總是這樣。例如，鏈接默認地會有下划線。如果您希望去掉超鏈接的下划線，可以使用以下 CSS 來做到這一點：
`a {text-decoration: none;}`

注意：如果顯式地用這樣一個規則去掉鏈接的下划線，那麼錨與正常文本之間在視覺上的唯一差別就是顏色（至少默認是這樣的，不過也不能完全保證其顏色肯定有區別）。

還可以在一個規則中結合多種裝飾。如果希望所有超鏈接既有下划線，又有上划線，則規則如下：
`a:link a:visited {text-decoration: underline overline;}`
不過要注意的是，如果兩個不同的裝飾都與同一元素匹配，勝出規則的值會完全取代另一個值。請考慮以下的規則：
`h2.stricken {text-decoration: line-through;}`
`h2 {text-decoration: underline overline;}`
對於給定的規則，所有 class 為 stricken 的 h2 元素都只有一個貫穿線裝飾，而沒有下划線和上划線，因為 text-decoration 值會替換而不是累積起來。

##處理空白符
white-space 屬性會影響到用戶代理對源文檔中的空格、換行和 tab 字符的處理。

通過使用該屬性，可以影響瀏覽器處理字之間和文本行之間的空白符的方式。從某種程度上講，默認的 XHTML 處理已經完成了空白符處理：它會把所有空白符合併為一個空格。所以給定以下標記，它在 Web 瀏覽器中顯示時，各個字之間只會顯示一個空格，同時忽略元素中的換行：

```html
<p>  This     paragraph has    many
    spaces           in it.</p>
```
可以用以下聲明顯式地設置這種默認行為：
`p {white-space: normal;}`

上面的規則告訴瀏覽器按照平常的做法去處理：丟掉多餘的空白符。如果給定這個值，換行字符（回車）會轉換為空格，一行中多個空格的序列也會轉換為一個空格。

##值 pre
不過，如果將 white-space 設置為 pre，受這個屬性影響的元素中，空白符的處理就有所不同，其行為就像 XHTML 的 pre 元素一樣；空白符不會被忽略。

如果 white-space 屬性的值為 pre，瀏覽器將會注意額外的空格，甚至回車。在這個方面，而且僅在這個方面，任何元素都可以相當於一個 pre 元素。

注意：經測試，IE 7 以及更早版本的瀏覽器不支持該值，因此請使用非 IE 的瀏覽器來查看上面的實例。

##值 nowrap
與之相對的值是 nowrap，它會防止元素中的文本換行，除非使用了一個 br 元素。在 CSS 中使用 nowrap 非常類似於 HTML 4 中用 `<td nowrap>` 將一個表單元格設置為不能換行，不過 white-space 值可以應用到任何元素。

##值 pre-wrap 和 pre-line
CSS2.1 引入了值 pre-wrap 和 pre-line，這在以前版本的 CSS 中是沒有的。這些值的作用是允許創作人員更好地控制空白符處理。

如果元素的 white-space 設置為 pre-wrap，那麼該元素中的文本會保留空白符序列，但是文本行會正常地換行。如果設置為這個值，源文本中的行分隔符以及生成的行分隔符也會保留。pre-line 與 pre-wrap 相反，會像正常文本中一樣合併空白符序列，但保留換行符。

注意：我們在 IE7 和 FireFox2.0 瀏覽器中測試了上面的兩個實例，但是結果是，值 pre-wrap 和 pre-line 都沒有得到很好的支持。

總結
下面的表格總結了 white-space 屬性的行為：

值|	空白符|	換行符|	自動換行
:--:|:--:|:--:|:--:
pre-line	|合併|	保留|	允許
normal	|合併	|忽略	|允許
nowrap	|合併|	忽略|	不允許
pre	|保留	|保留|	不允許
pre-wrap|	保留|	保留|	允許

##文本方向
如果您閱讀的是英文書籍，就會從左到右、從上到下地閱讀，這就是英文的流方向。不過，並不是所有語言都如此。我們知道古漢語就是從右到左來閱讀的，當然還包括希伯來語和阿拉伯語等等。CSS2 引入了一個屬性來描述其方向性。

direction 屬性影響塊級元素中文本的書寫方向、表中列佈局的方向、內容水平填充其元素框的方向、以及兩端對齊元素中最後一行的位置。

注釋：對於行內元素，只有當 unicode-bidi 屬性設置為 embed 或 bidi-override 時才會應用 direction 屬性。

direction 屬性有兩個值：ltr 和 rtl。大多數情況下，默認值是 ltr，顯示從左到右的文本。如果顯示從右到左的文本，應使用值 rtl。


##CSS 文本屬性

屬性|	描述
:--:|:--:
color|	設置文本顏色
direction|	設置文本方向。
line-height|	設置行高。
letter-spacing|	設置字符間距。
text-align	|對齊元素中的文本。
text-decoration	|向文本添加修飾。
text-indent	|縮進元素中文本的首行。
text-shadow	|設置文本陰影。CSS2 包含該屬性，但是 CSS2.1 沒有保留該屬性。
text-transform	|控制元素中的字母。
unicode-bidi	|設置文本方向。
white-space	|設置元素中空白的處理方式。
word-spacing	|設置字間距。

___

#CSS 字體

**CSS 字體屬性定義文本的字體系列、大小、加粗、風格（如斜體）和變形（如小型大寫字母）。**
##CSS 字體系列

在 CSS 中，有兩種不同類型的字體系列名稱：

* 通用字體系列 - 擁有相似外觀的字體系統組合（比如 "Serif" 或 "Monospace"）
* 特定字體系列 - 具體的字體系列（比如 "Times" 或 "Courier"）

除了各種特定的字體系列外，CSS 定義了 5 種通用字體系列：

* Serif 字體
* Sans-serif 字體
* Monospace 字體
* Cursive 字體
* Fantasy 字體

如果需要瞭解更多有關字體系列的知識，請閱讀 CSS 字體系列。

##指定字體系列
使用 font-family 屬性 定義文本的字體系列。

使用通用字體系列
如果你希望文檔使用一種 sans-serif 字體，但是你並不關心是哪一種字體，以下就是一個合適的聲明：
`body {font-family: sans-serif;}`

這樣用戶代理就會從 sans-serif 字體系列中選擇一個字體（如 Helvetica），並將其應用到 body 元素。因為有繼承，這種字體選擇還將應用到 body 元素中包含的所有元素，除非有一種更特定的選擇器將其覆蓋。

指定字體系列
除了使用通用的字體系列，您還可以通過 font-family 屬性設置更具體的字體。
下面的例子為所有 h1 元素設置了 Georgia 字體：
`h1 {font-family: Georgia;}`

這樣的規則同時會產生另外一個問題，如果用戶代理上沒有安裝 Georgia 字體，就只能使用用戶代理的默認字體來顯示 h1 元素。
我們可以通過結合特定字體名和通用字體系列來解決這個問題：
`h1 {font-family: Georgia, serif;}`

如果讀者沒有安裝 Georgia，但安裝了 Times 字體（serif 字體系列中的一種字體），用戶代理就可能對 h1 元素使用 Times。儘管 Times 與 Georgia 並不完全匹配，但至少足夠接近。

因此，我們建議在所有 font-family 規則中都提供一個通用字體系列。這樣就提供了一條後路，在用戶代理無法提供與規則匹配的特定字體時，就可以選擇一個候選字體。

如果您對字體非常熟悉，也可以為給定的元素指定一系列類似的字體。要做到這一點，需要把這些字體按照優先順序排列，然後用逗號進行連接：

```css
p {font-family: Times, TimesNR, 'New Century Schoolbook',
     Georgia, 'New York', serif;}
```

根據這個列表，用戶代理會按所列的順序查找這些字體。如果列出的所有字體都不可用，就會簡單地選擇一種可用的 serif 字體。

使用引號
您也許已經注意到了，上面的例子中使用了單引號。只有當字體名中有一個或多個空格（比如 New York），或者如果字體名包括 # 或 $ 之類的符號，才需要在 font-family 聲明中加引號。

單引號或雙引號都可以接受。但是，如果把一個 font-family 屬性放在 HTML 的 style 屬性中，則需要使用該屬性本身未使用的那種引號：

```html
<p style="font-family: Times, TimesNR, 'New Century Schoolbook', Georgia,
 'New York', serif;">...</p>
```

##字體風格
font-style 屬性最常用於規定斜體文本。
該屬性有三個值：

* normal - 文本正常顯示
* italic - 文本斜體顯示
* oblique - 文本傾斜顯示

實例

```css
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

##italic 和 oblique 的區別
font-style 非常簡單：用於在 normal 文本、italic 文本和 oblique 文本之間選擇。唯一有點複雜的是明確 italic 文本和 oblique 文本之間的差別。

斜體（italic）是一種簡單的字體風格，對每個字母的結構有一些小改動，來反映變化的外觀。與此不同，傾斜（oblique）文本則是正常竪直文本的一個傾斜版本。

通常情況下，italic 和 oblique 文本在 web 瀏覽器中看上去完全一樣。

##字體變形
font-variant 屬性可以設定小型大寫字母。
小型大寫字母不是一般的大寫字母，也不是小寫字母，這種字母採用不同大小的大寫字母。

實例
`p {font-variant:small-caps;}`

##字體加粗
font-weight 屬性設置文本的粗細。

使用 bold 關鍵字可以將文本設置為粗體。

關鍵字 100 ~ 900 為字體指定了 9 級加粗度。如果一個字體內置了這些加粗級別，那麼這些數字就直接映射到預定義的級別，100 對應最細的字體變形，900 對應最粗的字體變形。數字 400 等價於 normal，而 700 等價於 bold。

如果將元素的加粗設置為 bolder，瀏覽器會設置比所繼承值更粗的一個字體加粗。與此相反，關鍵詞 lighter 會導致瀏覽器將加粗度下移而不是上移。
實例

```css
p.normal {font-weight:normal;}
p.thick {font-weight:bold;}
p.thicker {font-weight:900;}
```

##字體大小
font-size 屬性設置文本的大小。
有能力管理文本的大小在 web 設計領域很重要。但是，您不應當通過調整文本大小使段落看上去像標題，或者使標題看上去像段落。

請始終使用正確的 HTML 標題，比如使用 `<h1>` - `<h6>` 來標記標題，使用 `<p>` 來標記段落。
font-size 值可以是絕對或相對值。

絕對值：

* 將文本設置為指定的大小
* 不允許用戶在所有瀏覽器中改變文本大小（不利於可用性）
* 絕對大小在確定了輸出的物理尺寸時很有用

相對大小：

* 相對於周圍的元素來設置大小
* 允許用戶在瀏覽器改變文本大小

注意：如果您沒有規定字體大小，普通文本（比如段落）的默認大小是 16 像素 (16px=1em)。

使用像素來設置字體大小
通過像素設置文本大小，可以對文本大小進行完全控制：
實例

```css
h1 {font-size:60px;}
h2 {font-size:40px;}
p {font-size:14px;}
```

在 Firefox, Chrome, and Safari 中，可以重新調整以上例子的文本大小，但是在 Internet Explorer 中不行。
雖然可以通過瀏覽器的縮放工具調整文本大小，但是這實際上是對整個頁面的調整，而不僅限於文本。

##使用 em 來設置字體大小

如果要避免在 Internet Explorer 中無法調整文本的問題，許多開發者使用 em 單位代替 pixels。

W3C 推薦使用 em 尺寸單位。

1em 等於當前的字體尺寸。如果一個元素的 font-size 為 16 像素，那麼對於該元素，1em 就等於 16 像素。在設置字體大小時，em 的值會相對於父元素的字體大小改變。

瀏覽器中默認的文本大小是 16 像素。因此 1em 的默認尺寸是 16 像素。

可以使用下面這個公式將像素轉換為 em：pixels/16=em
（注：16 等於父元素的默認字體大小，假設父元素的 font-size 為 20px，那麼公式需改為：pixels/20=em）
實例

```css
h1 {font-size:3.75em;} /* 60px/16=3.75em */
h2 {font-size:2.5em;}  /* 40px/16=2.5em */
p {font-size:0.875em;} /* 14px/16=0.875em */
```

在上面的例子中，以 em 為單位的文本大小與前一個例子中以像素計的文本是相同的。不過，如果使用 em 單位，則可以在所有瀏覽器中調整文本大小。

不幸的是，在 IE 中仍存在問題。在重設文本大小時，會比正常的尺寸更大或更小。
結合使用百分比和 EM

在所有瀏覽器中均有效的方案是為 body 元素（父元素）以百分比設置默認的 font-size 值：
實例

```css
body {font-size:100%;}
h1 {font-size:3.75em;}
h2 {font-size:2.5em;}
p {font-size:0.875em;}
```

我們的代碼非常有效。在所有瀏覽器中，可以顯示相同的文本大小，並允許所有瀏覽器縮放文本的大小。

##CSS 字體屬性

屬性|	描述
:--:|:--:
font|	簡寫屬性。作用是把所有針對字體的屬性設置在一個聲明中。
font-family|	設置字體系列。
font-size|	設置字體的尺寸。
font-size-adjust|	當首選字體不可用時，對替換字體進行智能縮放。（CSS2.1 已刪除該屬性。）
font-stretch	|對字體進行水平拉伸。（CSS2.1 已刪除該屬性。）
font-style|	設置字體風格。
font-variant|	以小型大寫字體或者正常字體顯示文本。
font-weight|	設置字體的粗細。

___

#CSS 鏈接
**我們能夠以不同的方法為鏈接設置樣式。**

##設置鏈接的樣式
能夠設置鏈接樣式的 CSS 屬性有很多種（例如 color, font-family, background 等等）。
鏈接的特殊性在於能夠根據它們所處的狀態來設置它們的樣式。
鏈接的四種狀態：

* a:link - 普通的、未被訪問的鏈接
* a:visited - 用戶已訪問的鏈接
* a:hover - 鼠標指針位於鏈接的上方
* a:active - 鏈接被點擊的時刻

實例

```css
a:link {color:#FF0000;}		/* 未被訪問的鏈接 */
a:visited {color:#00FF00;}	/* 已被訪問的鏈接 */
a:hover {color:#FF00FF;}	/* 鼠標指針移動到鏈接上 */
a:active {color:#0000FF;}	/* 正在被點擊的鏈接 */
```

當為鏈接的不同狀態設置樣式時，請按照以下次序規則：

* a:hover 必須位於 a:link 和 a:visited 之後
* a:active 必須位於 a:hover 之後

##常見的鏈接樣式
在上面的例子中，鏈接根據其狀態改變顏色。
讓我們看看其他幾種常見的設置鏈接樣式的方法：

###文本修飾
text-decoration 屬性大多用於去掉鏈接中的下划線：

實例

```css
a:link {text-decoration:none;}
a:visited {text-decoration:none;}
a:hover {text-decoration:underline;}
a:active {text-decoration:underline;}
```

###背景色
background-color 屬性規定鏈接的背景色：

實例

```css
a:link {background-color:#B2FF99;}
a:visited {background-color:#FFFF85;}
a:hover {background-color:#FF704D;}
a:active {background-color:#FF704D;}
```
___

#CSS 列表
**CSS 列表屬性允許你放置、改變列表項標誌，或者將圖像作為列表項標誌。**
##CSS 列表
從某種意義上講，不是描述性的文本的任何內容都可以認為是列表。人口普查、太陽系、家譜、參觀菜單，甚至你的所有朋友都可以表示為一個列表或者是列表的列表。

由於列表如此多樣，這使得列表相當重要，所以說，CSS 中列表樣式不太豐富確實是一大憾事。

###列表類型
要影響列表的樣式，最簡單（同時支持最充分）的辦法就是改變其標誌類型。

例如，在一個無序列表中，列表項的標誌 (marker) 是出現在各列表項旁邊的圓點。在有序列表中，標誌可能是字母、數字或另外某種計數體系中的一個符號。

要修改用於列表項的標誌類型，可以使用屬性 list-style-type：

```css
ul {list-style-type : square}
```

上面的聲明把無序列表中的列表項標誌設置為方塊。

###列表項圖像
有時，常規的標誌是不夠的。你可能想對各標誌使用一個圖像，這可以利用 list-style-image 屬性做到：

```css
ul li {list-style-image : url(xxx.gif)}
```
只需要簡單地使用一個 url() 值，就可以使用圖像作為標誌。

###列表標誌位置
CSS2.1 可以確定標誌出現在列表項內容之外還是內容內部。這是利用 list-style-position 完成的。

###簡寫列表樣式
為簡單起見，可以將以上 3 個列表樣式屬性合併為一個方便的屬性：list-style，就像這樣：

```css
li {list-style : url(example.gif) square inside}
```

list-style 的值可以按任何順序列出，而且這些值都可以忽略。只要提供了一個值，其它的就會填入其默認值。

##CSS 列表屬性(list)

屬性|	描述
:--:|:--:
list-style|	簡寫屬性。用於把所有用於列表的屬性設置於一個聲明中。
list-style-image|	將圖象設置為列表項標誌。
list-style-position|	設置列表中列表項標誌的位置。
list-style-type|	設置列表項標誌的類型。

___

#CSS 表格
**CSS 表格屬性可以幫助您極大地改善表格的外觀。**
##表格邊框
如需在 CSS 中設置表格邊框，請使用 border 屬性。
下面的例子為 table、th 以及 td 設置了藍色邊框：

```css
table, th, td
  {
  border: 1px solid blue;
  }
```

請注意，上例中的表格具有雙線條邊框。這是由於 table、th 以及 td 元素都有獨立的邊框。
如果需要把表格顯示為單線條邊框，請使用 border-collapse 屬性。

##折疊邊框
border-collapse 屬性設置是否將表格邊框折疊為單一邊框：

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

##表格寬度和高度
通過 width 和 height 屬性定義表格的寬度和高度。
下面的例子將表格寬度設置為 100%，同時將 th 元素的高度設置為 50px：

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

##表格文本對齊
text-align 和 vertical-align 屬性設置表格中文本的對齊方式。
text-align 屬性設置水平對齊方式，比如左對齊、右對齊或者居中：

```css
td
  {
  text-align:right;
  }
```

vertical-align 屬性設置垂直對齊方式，比如頂部對齊、底部對齊或居中對齊：

```css
td
  {
  height:50px;
  vertical-align:bottom;
  }
```

##表格內邊距
如需控制表格中內容與邊框的距離，請為 td 和 th 元素設置 padding 屬性：

```css
td
  {
  padding:15px;
  }
```

##表格顏色
下面的例子設置邊框的顏色，以及 th 元素的文本和背景顏色：

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

##CSS Table 屬性
屬性|	描述
:--:|:--:
border-collapse|	設置是否把表格邊框合併為單一的邊框。
border-spacing|	設置分隔單元格邊框的距離。
caption-side|	設置表格標題的位置。
empty-cells|	設置是否顯示表格中的空單元格。
table-layout|	設置顯示單元、行和列的算法。

___

#CSS 輪廓
**輪廓（outline）是繪制於元素周圍的一條線，位於邊框邊緣的外圍，可起到突出元素的作用。**
**CSS outline 屬性規定元素輪廓的樣式、顏色和寬度。**


##CSS 邊框屬性
"CSS" 列中的數字指示哪個 CSS 版本定義了該屬性。

屬性|	描述|	CSS
:--:|:--:|:--:
outline	|在一個聲明中設置所有的輪廓屬性。	|2
outline-color|	設置輪廓的顏色。	|2
outline-style|	設置輪廓的樣式。	|2
outline-width|	設置輪廓的寬度。	|2

