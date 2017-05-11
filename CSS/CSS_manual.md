#CSS 參考手冊

##CSS3 動畫屬性（Animation）

屬性|	描述|	CSS
:--:|:--:|:--:
@keyframes|	規定動畫。|	3
animation|	所有動畫屬性的簡寫屬性，除了 animation-play-state 屬性。	|3
animation-name|	規定 @keyframes 動畫的名稱。	|3
animation-duration|	規定動畫完成一個週期所花費的秒或毫秒。	|3
animation-timing-function|	規定動畫的速度曲線。	|3
animation-delay|	規定動畫何時開始。	|3
animation-iteration-count|	規定動畫被播放的次數。	|3
animation-direction|	規定動畫是否在下一週期逆向地播放。	|3
animation-play-state|	規定動畫是否正在運行或暫停。	|3
animation-fill-mode|	規定對象動畫時間之外的狀態。	|3

##CSS 背景屬性（Background）

屬性|	描述|	CSS
:--:|:--:|:--:
background|	在一個聲明中設置所有的背景屬性。	|1
background-attachment|	設置背景圖像是否固定或者隨著頁面的其餘部分滾動。	|1
background-color|	設置元素的背景顏色。	|1
background-image|	設置元素的背景圖像。	|1
background-position|	設置背景圖像的開始位置。	|1
background-repeat|	設置是否及如何重復背景圖像。	|1
background-clip	|規定背景的繪制區域。	|3
background-origin|	規定背景圖片的定位區域。	|3
background-size	|規定背景圖片的尺寸。	|3

##CSS 邊框屬性（Border 和 Outline）

屬性	|描述|	CSS
:--:|:--:|:--:
border|	在一個聲明中設置所有的邊框屬性。	|1
border-bottom|	在一個聲明中設置所有的下邊框屬性。	|1
border-bottom-color|	設置下邊框的顏色。	|2
border-bottom-style|	設置下邊框的樣式。	|2
border-bottom-width|	設置下邊框的寬度。	|1
border-color|	設置四條邊框的顏色。	|1
border-left|	在一個聲明中設置所有的左邊框屬性。	|1
border-left-color|	設置左邊框的顏色。	|2
border-left-style|	設置左邊框的樣式。	|2
border-left-width|	設置左邊框的寬度。	|1
border-right|	在一個聲明中設置所有的右邊框屬性。	|1
border-right-color|	設置右邊框的顏色。	|2
border-right-style|	設置右邊框的樣式。	|2
border-right-width|	設置右邊框的寬度。	|1
border-style|	設置四條邊框的樣式。	|1
border-top|	在一個聲明中設置所有的上邊框屬性。	|1
border-top-color|	設置上邊框的顏色。	|2
border-top-style|	設置上邊框的樣式。	|2
border-top-width|	設置上邊框的寬度。	|1
border-width|	設置四條邊框的寬度。	|1
outline	|在一個聲明中設置所有的輪廓屬性。	|2
outline-color|	設置輪廓的顏色。	|2
outline-style|	設置輪廓的樣式。	|2
outline-width|	設置輪廓的寬度。	|2
border-bottom-left-radius|	定義邊框左下角的形狀。	|3
border-bottom-right-radius|	定義邊框右下角的形狀。	|3
border-image|	簡寫屬性，設置所有 border-image-* 屬性。	|3
border-image-outset|	規定邊框圖像區域超出邊框的量。	|3
border-image-repeat|	圖像邊框是否應平鋪(repeated)、鋪滿(rounded)或拉伸(stretched)。	|3
border-image-slice|	規定圖像邊框的向內偏移。	|3
border-image-source|	規定用作邊框的圖片。	|3
border-image-width|	規定圖片邊框的寬度。	|3
border-radius|	簡寫屬性，設置所有四個 border-*-radius 屬性。	|3
border-top-left-radius|	定義邊框左上角的形狀。	|3
border-top-right-radius|	定義邊框右下角的形狀。	|3
box-decoration-break	|	|3
box-shadow|	向方框添加一個或多個陰影。	|3

##Box 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
overflow-x|	如果內容溢出了元素內容區域，是否對內容的左/右邊緣進行裁剪。	|3
overflow-y|	如果內容溢出了元素內容區域，是否對內容的上/下邊緣進行裁剪。	|3
overflow-style|	規定溢出元素的首選滾動方法。	|3
rotation|	圍繞由 rotation-point 屬性定義的點對元素進行旋轉。	|3
rotation-point|	定義距離上左邊框邊緣的偏移點。	|3

##Color 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
color-profile|	允許使用源的顏色配置文件的默認以外的規範。	|3
opacity|	規定書簽的級別。	|3
rendering-intent|	允許使用顏色配置文件渲染意圖的默認以外的規範。	|3

##Content for Paged Media 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
bookmark-label|	規定書簽的標記。	|3
bookmark-level|	規定書簽的級別。	|3
bookmark-target|	規定書簽鏈接的目標。	|3
float-offset|	將元素放在 float 屬性通常放置的位置的相反方向。	|3
hyphenate-after|	規定連字單詞中連字符之後的最小字符數。	|3
hyphenate-before|	規定連字單詞中連字符之前的最小字符數。	|3
hyphenate-character|	規定當發生斷字時顯示的字符串。	|3
hyphenate-lines|	指示元素中連續斷字連線的最大數。	|3
hyphenate-resource|	規定幫助瀏覽器確定斷字點的外部資源（逗號分隔的列表）。	|3
hyphens|	設置如何對單詞進行拆分，以改善段落的佈局。	|3
image-resolution|	規定圖像的正確分辨率。	|3
marks|	向文檔添加裁切標記或十字標記。|	3
string-set||		3

##CSS 尺寸屬性（Dimension）

屬性|	描述|	CSS
:--:|:--:|:--:
height|	設置元素高度。	|1
max-height|	設置元素的最大高度。	|2
max-width|	設置元素的最大寬度。	|2
min-height|	設置元素的最小高度。	|2
min-width|	設置元素的最小寬度。	|2
width|	設置元素的寬度。	|1

##可伸縮框屬性（Flexible Box）

屬性|	描述|	CSS
:--:|:--:|:--:
box-align|	規定如何對齊框的子元素。	|3
box-direction|	規定框的子元素的顯示方向。	|3
box-flex|	規定框的子元素是否可伸縮。	|3
box-flex-group|	將可伸縮元素分配到柔性分組。	|3
box-lines|	規定當超出父元素框的空間時，是否換行顯示。	|3
box-ordinal-group|	規定框的子元素的顯示次序。	|3
box-orient|	規定框的子元素是否應水平或垂直排列。	|3
box-pack|	規定水平框中的水平位置或者垂直框中的垂直位置。	|3

##CSS 字體屬性（Font）

屬性|	描述|	CSS
:--:|:--:|:--:
font|	在一個聲明中設置所有字體屬性。	|1
font-family|	規定文本的字體系列。	|1
font-size|	規定文本的字體尺寸。	|1
font-size-adjust|	為元素規定 aspect 值。|	2
font-stretch|	收縮或拉伸當前的字體系列。	|2
font-style|	規定文本的字體樣式。	|1
font-variant|	規定是否以小型大寫字母的字體顯示文本。	|1
font-weight|	規定字體的粗細。	|1

##內容生成（Generated Content）

屬性|	描述|	CSS
:--:|:--:|:--:
content	與 :before 以及 :after| 偽元素配合使用，來插入生成內容。	|2
counter-increment|	遞增或遞減一個或多個計數器。	|2
counter-reset|	創建或重置一個或多個計數器。	|2
quotes|	設置嵌套引用的引號類型。	|2
crop|	允許被替換元素僅僅是對象的矩形區域，而不是整個對象。	|3
move-to|	從流中刪除元素，然後在文檔中後面的點上重新插入。	|3
page-policy|	確定元素基於頁面的 occurrence 應用於計數器還是字符串值。	|3

##Grid 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
grid-columns|	規定網格中每個列的寬度。	|3
grid-rows|	規定網格中每個列的高度。	|3

##Hyperlink 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
target|	簡寫屬性，設置target-name、target-new以及target-position屬性。	|3
target-name|	規定在何處打開鏈接（鏈接的目標）。	|3
target-new|	規定目標鏈接在新窗口還是在已有窗口的新標籤頁中打開。	|3
target-position|	規定在何處放置新的目標鏈接。	|3

##CSS 列表屬性（List）

屬性|	描述|	CSS
:--:|:--:|:--:
list-style|	在一個聲明中設置所有的列表屬性。	|1
list-style-image|	將圖象設置為列表項標記。	|1
list-style-position|	設置列表項標記的放置位置。	|1
list-style-type|	設置列表項標記的類型。	|1
marker-offset	|| 	2

##CSS 外邊距屬性（Margin）

屬性|	描述|	CSS
:--:|:--:|:--:
margin|	在一個聲明中設置所有外邊距屬性。	|1
margin-bottom|	設置元素的下外邊距。	|1
margin-left|	設置元素的左外邊距。	|1
margin-right|	設置元素的右外邊距。	|1
margin-top|	設置元素的上外邊距。	|1

##Marquee 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
marquee-direction|	設置移動內容的方向。	|3
marquee-play-count|	設置內容移動多少次。	|3
marquee-speed|	設置內容滾動得多快。	|3
marquee-style|	設置移動內容的樣式。	|3

##多列屬性（Multi-column）

屬性|	描述|	CSS
:--:|:--:|:--:
column-count|	規定元素應該被分隔的列數。	|3
column-fill|	規定如何填充列。	|3
column-gap|	規定列之間的間隔。	|3
column-rule|	設置所有 column-rule-* 屬性的簡寫屬性。	|3
column-rule-color|	規定列之間規則的顏色。	|3
column-rule-style|	規定列之間規則的樣式。	|3
column-rule-width|	規定列之間規則的寬度。	|3
column-span|	規定元素應該橫跨的列數。	|3
column-width|	規定列的寬度。	|3
columns|	規定設置 column-width 和 column-count 的簡寫屬性。	|3

##CSS 內邊距屬性（Padding）

屬性|	描述|	CSS
:--:|:--:|:--:
padding|	在一個聲明中設置所有內邊距屬性。|	1
padding-bottom|	設置元素的下內邊距。	|1
padding-left|	設置元素的左內邊距。	|1
padding-right|	設置元素的右內邊距。	|1
padding-top|	設置元素的上內邊距。	|1

##Paged Media 屬性

屬性|	描述|	CSS
:--:|:--:|:--:
fit|	示意如何對width和height屬性均不是auto的被替換元素進行縮放。	|3
fit-position|	定義盒內對象的對齊方式。	|3
image-orientation|	規定用戶代理應用於圖像的順時針方向旋轉。	|3
page|	規定元素應該被顯示的頁面特定類型。	|3
size|	規定頁面內容包含框的尺寸和方向。	|3

##CSS 定位屬性（Positioning）

屬性|	描述|	CSS
:--:|:--:|:--:
bottom|	設置定位元素下外邊距邊界與其包含塊下邊界之間的偏移。	|2
clear|	規定元素的哪一側不允許其他浮動元素。	|1
clip|	剪裁絕對定位元素。	|2
cursor|	規定要顯示的光標的類型（形狀）。	|2
display|	規定元素應該生成的框的類型。	|1
float|	規定框是否應該浮動。	|1
left|	設置定位元素左外邊距邊界與其包含塊左邊界之間的偏移。	|2
overflow|	規定當內容溢出元素框時發生的事情。	|2
position|	規定元素的定位類型。	|2
right|	設置定位元素右外邊距邊界與其包含塊右邊界之間的偏移。	|2
top|	設置定位元素的上外邊距邊界與其包含塊上邊界之間的偏移。	|2
vertical-align|	設置元素的垂直對齊方式。	|1
visibility|	規定元素是否可見。	|2
z-index|	設置元素的堆疊順序。	|2

##CSS 打印屬性（Print）

屬性|	描述|	CSS
:--:|:--:|:--:
orphans|	設置當元素內部發生分頁時必須在頁面底部保留的最少行數。	|2
page-break-after|	設置元素後的分頁行為。	|2
page-break-before|	設置元素前的分頁行為。	|2
page-break-inside|	設置元素內部的分頁行為。	|2
widows|	設置當元素內部發生分頁時必須在頁面頂部保留的最少行數。	|2

##CSS 表格屬性（Table）

屬性|	描述	|CSS
:--:|:--:|:--:
border-collapse|	規定是否合併表格邊框。	|2
border-spacing|	規定相鄰單元格邊框之間的距離。	|2
caption-side|	規定表格標題的位置。	|2
empty-cells|	規定是否顯示表格中的空單元格上的邊框和背景。	|2
table-layout|	設置用於表格的佈局算法。	|2

##CSS 文本屬性（Text）

屬性|	描述|	CSS
:--:|:--:|:--:
color|	設置文本的顏色。	|1
direction|	規定文本的方向 / 書寫方向。	|2
letter-spacing|	設置字符間距。	|1
line-height|	設置行高。	|1
text-align|	規定文本的水平對齊方式。	|1
text-decoration|	規定添加到文本的裝飾效果。	|1
text-indent|	規定文本塊首行的縮進。	|1
text-shadow|	規定添加到文本的陰影效果。	|2
text-transform|	控制文本的大小寫。	|1
unicode-bidi|	設置文本方向。	|2
white-space|	規定如何處理元素中的空白。	|1
word-spacing|	設置單詞間距。	|1
hanging-punctuation|	規定標點字符是否位於線框之外。	|3
punctuation-trim|	規定是否對標點字符進行修剪。	|3
text-align-last|	設置如何對齊最後一行或緊挨著強制換行符之前的行。	|3
text-emphasis|	向元素的文本應用重點標記以及重點標記的前景色。	|3
text-justify|	規定當 text-align 設置為 "justify" 時所使用的對齊方法。	|3
text-outline|	規定文本的輪廓。	|3
text-overflow|	規定當文本溢出包含元素時發生的事情。	|3
text-shadow|	向文本添加陰影。	|3
text-wrap|	規定文本的換行規則。	|3
word-break|	規定非中日韓文本的換行規則。	|3
word-wrap|	允許對長的不可分割的單詞進行分割並換行到下一行。	|3

##2D/3D 轉換屬性（Transform）

屬性|	描述|	CSS
:--:|:--:|:--:
transform|	向元素應用 2D 或 3D 轉換。	|3
transform-origin|	允許你改變被轉換元素的位置。	|3
transform-style|	規定被嵌套元素如何在 3D 空間中顯示。	|3
perspective|	規定 3D 元素的透視效果。	|3
perspective-origin|	規定 3D 元素的底部位置。	|3
backface-visibility|	定義元素在不面對屏幕時是否可見。	|3

##過渡屬性（Transition）

屬性|	描述|	CSS
:--:|:--:|:--:
transition|	簡寫屬性，用於在一個屬性中設置四個過渡屬性。	|3
transition-property|	規定應用過渡的 CSS 屬性的名稱。	|3
transition-duration|	定義過渡效果花費的時間。	|3
transition-timing-function|	規定過渡效果的時間曲線。	|3
transition-delay|	規定過渡效果何時開始。	|3

##用戶界面屬性（User-interface）

屬性|	描述|	CSS
:--:|:--:|:--:
appearance|	允許您將元素設置為標準用戶界面元素的外觀	|3
box-sizing|	允許您以確切的方式定義適應某個區域的具體內容。	|3
icon	|為創作者提供使用圖標化等價物來設置元素樣式的能力。	|3
nav-down|	規定在使用 arrow-down 導航鍵時向何處導航。	|3
nav-index|	設置元素的 tab 鍵控制次序。	|3
nav-left|	規定在使用 arrow-left 導航鍵時向何處導航。	|3
nav-right|	規定在使用 arrow-right 導航鍵時向何處導航。	|3
nav-up|	規定在使用 arrow-up 導航鍵時向何處導航。	|3
outline-offset|	對輪廓進行偏移，並在超出邊框邊緣的位置繪制輪廓。	|3
resize|	規定是否可由用戶對元素的尺寸進行調整。	|3

##CSS 選擇器參考手冊
在 CSS 中，選擇器是一種模式，用於選擇需要添加樣式的元素。
"CSS" 列指示該屬性是在哪個 CSS 版本中定義的。（CSS1、CSS2 還是 CSS3。）

選擇器|	例子|	例子描述|	CSS
:--:|:--:|:--:|:--:
.class|	.intro|	選擇 class="intro" 的所有元素。|	1
#id|	#firstname|	選擇 id="firstname" 的所有元素。	|1
*|	*	|選擇所有元素。	|2
element	|p	|選擇所有 `<p>` 元素。	|1
element,element	|div,p|	選擇所有 `<div>` 元素和所有 `<p>` 元素。	|1
element element	|div p	選擇 `<div>` 元素內部的所有 `<p>` 元素。	|1
element>element	|div>p	|選擇父元素為 `<div>` 元素的所有 `<p>` 元素。	|2
element+element	|div+p|	選擇緊接在 `<div>` 元素之後的所有 `<p>` 元素。	|2
[attribute]	|[target]|	選擇帶有 target 屬性所有元素。	|2
[attribute=value]|	[target=_blank]	|選擇 target="_blank" 的所有元素。	|2
[attribute~=value]|	[title~=flower]|	選擇 title 屬性包含單詞 "flower" 的所有元素。	|2
[attribute|=value]	|[lang|=en]|	選擇 lang 屬性值以 "en" 開頭的所有元素。	|2
:link|	a:link|	選擇所有未被訪問的鏈接。	|1
:visited|	a:visited|	選擇所有已被訪問的鏈接。	|1
:active|	a:active|	選擇活動鏈接。	|1
:hover|	a:hover|	選擇鼠標指針位於其上的鏈接。	|1
:focus|	input:focus|	選擇獲得焦點的 input 元素。	|2
:first-letter|	p:first-letter|	選擇每個 `<p>` 元素的首字母。	|1
:first-line|	p:first-line	|選擇每個 `<p>` 元素的首行。	|1
:first-child|	p:first-child|	選擇屬於父元素的第一個子元素的每個 `<p>` 元素。	|2
:before|	p:before|	在每個 `<p>` 元素的內容之前插入內容。	|2
:after|	p:after	|在每個 `<p>` 元素的內容之後插入內容。	|2
:lang(language)|	p:lang(it)|	選擇帶有以 "it" 開頭的 lang 屬性值的每個 `<p>` 元素。	|2
element1~element2|	p~ul|	選擇前面有 `<p>` 元素的每個 `<ul>` 元素。	|3
[attribute^=value]|	a[src^="https"]	|選擇其 src 屬性值以 "https" 開頭的每個 `<a>` 元素。	|3
[attribute$=value]|	a[src$=".pdf"]	|選擇其 src 屬性以 ".pdf" 結尾的所有 `<a>` 元素。	|3
[attribute*=value]|	a[src*="abc"]|	選擇其 src 屬性中包含 "abc" 子串的每個 `<a>` 元素。	|3
:first-of-type|	p:first-of-type|	選擇屬於其父元素的首個 `<p>` 元素的每個 `<p>` 元素。	|3
:last-of-type	|p:last-of-type|	選擇屬於其父元素的最後 `<p>` 元素的每個 `<p>` 元素。	|3
:only-of-type|	p:only-of-type|	選擇屬於其父元素唯一的 `<p>` 元素的每個 `<p>` 元素。	|3
:only-child	|p:only-child	|選擇屬於其父元素的唯一子元素的每個 `<p>` 元素。	|3
:nth-child(n)|	p:nth-child(2)|	選擇屬於其父元素的第二個子元素的每個 `<p>` 元素。	|3
:nth-last-child(n)|	p:nth-last-child(2)|	同上，從最後一個子元素開始計數。	|3
:nth-of-type(n)|	p:nth-of-type(2)	|選擇屬於其父元素第二個 `<p>` 元素的每個 `<p>` 元素。	|3
:nth-last-of-type(n)	|p:nth-last-of-type(2)|	同上，但是從最後一個子元素開始計數。	|3
:last-child	|p:last-child	|選擇屬於其父元素最後一個子元素每個 `<p>` 元素。	|3
:root	|:root|	選擇文檔的根元素。	|3
:empty|	p:empty|	選擇沒有子元素的每個 `<p>` 元素（包括文本節點）。	|3
:target|	#news:target|	選擇當前活動的 #news 元素。	|3
:enabled|	input:enabled|	選擇每個啓用的 `<input>` 元素。	|3
:disabled|	input:disabled	|選擇每個禁用的 `<input>` 元素|	3
:checked|input:checked	|選擇每個被選中的 `<input>` 元素。	|3
:not(selector)	|:not(p)|	選擇非 `<p>` 元素的每個元素。	|3
::selection|	::selection|	選擇被用戶選取的元素部分。	|3

