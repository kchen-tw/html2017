通過 HTML DOM，可訪問 JavaScript HTML 文檔的所有元素。

## HTML DOM （文檔對象模型）

當網頁被加載時，瀏覽器會創建頁面的文檔對象模型（Document Object Model）。
HTML DOM 模型被構造為對象的樹。

###HTML DOM 樹
![DOM TREE](https://www.w3schools.com/js/pic_htmltree.gif)

###DOM HTML 樹
通過可編程的對象模型，JavaScript 獲得了足夠的能力來創建動態的 HTML。
* JavaScript 能夠改變頁面中的所有 HTML 元素
* JavaScript 能夠改變頁面中的所有 HTML 屬性
* JavaScript 能夠改變頁面中的所有 CSS 樣式
* JavaScript 能夠對頁面中的所有事件做出反應
###查找 HTML 元素
通常，通過 JavaScript，您需要操作 HTML 元素。
為了做到這件事情，您必須首先找到該元素。有三種方法來做這件事：
* 通過 id 找到 HTML 元素
* 通過標籤名找到 HTML 元素
* 通過類名找到 HTML 元素

####通過 id 查找 HTML 元素
在 DOM 中查找 HTML 元素的最簡單的方法，是通過使用元素的 id。
本例查找 id="intro" 元素：
`var x=document.getElementById("intro");`

如果找到該元素，則該方法將以對象（在 x 中）的形式返回該元素。
如果未找到該元素，則 x 將包含 null。
####通過標籤名查找 HTML 元素
本例查找 id="main" 的元素，然後查找 "main" 中的所有 `<p>` 元素：
```
var x=document.getElementById("main");
var y=x.getElementsByTagName("p");
```

HTML DOM 允許 JavaScript 改變 HTML 元素的內容。
###改變 HTML 輸出流
JavaScript 能夠創建動態的 HTML 內容：
今天的日期是： `Sat Mar 11 2017 15:32:52 GMT+0800 (CST)`
在 JavaScript 中，document.write() 可用於直接向 HTML 輸出流寫內容。
```html
<!DOCTYPE html>
<html>
<body>

<script>
document.write(Date());
</script>

</body>
</html>
```

提示：絕不要使用在文檔加載之後使用 document.write()。這會覆蓋該文檔。
###改變 HTML 內容
修改 HTML 內容的最簡單的方法時使用 innerHTML 屬性。
如需改變 HTML 元素的內容，請使用這個語法：
`document.getElementById(id).innerHTML=new HTML`
本例改變了 `<p>` 元素的內容：
```html
<html>
<body>

<p id="p1">Hello World!</p>

<script>
document.getElementById("p1").innerHTML="New text!";
</script>

</body>
</html>
親自試一試
實例
本例改變了 <h1> 元素的內容：
<!DOCTYPE html>
<html>
<body>

<h1 id="header">Old Header</h1>

<script>
var element=document.getElementById("header");
element.innerHTML="New Header";
</script>

</body>
</html>
```
例子解釋：
上面的 HTML 文檔含有 id="header" 的 `<h1>` 元素
我們使用 HTML DOM 來獲得 id="header" 的元素
JavaScript 更改此元素的內容 (innerHTML)
####改變 HTML 屬性
如需改變 HTML 元素的屬性，請使用這個語法：
`document.getElementById(id).attribute=new value`
本例改變了 `<img>` 元素的 src 屬性：
```html
<!DOCTYPE html>
<html>
<body>

<img id="image" src="smiley.gif">

<script>
document.getElementById("image").src="landscape.jpg";
</script>

</body>
</html>
```
例子解釋：
上面的 HTML 文檔含有 id="image" 的 `<img>` 元素
我們使用 HTML DOM 來獲得 id="image" 的元素
JavaScript 更改此元素的屬性（把 "smiley.gif" 改為 "landscape.jpg"）

HTML DOM 允許 JavaScript 改變 HTML 元素的樣式。
###改變 HTML 樣式
如需改變 HTML 元素的樣式，請使用這個語法：
`document.getElementById(id).style.property=new style`
下面的例子會改變 `<p>` 元素的樣式：
```html
<p id="p2">Hello World!</p>

<script>
document.getElementById("p2").style.color="blue";
</script>
```
本例改變了 id="id1" 的 HTML 元素的樣式，當用戶點擊按鈕時：
```html
<h1 id="id1">My Heading 1</h1>

<button type="button" onclick="document.getElementById('id1').style.color='red'">
點擊這裡
</button>
```


HTML DOM 使 JavaScript 有能力對 HTML 事件做出反應。
###對事件做出反應
我們可以在事件發生時執行 JavaScript，比如當用戶在 HTML 元素上點擊時。
如需在用戶點擊某個元素時執行代碼，請向一個 HTML 事件屬性添加 JavaScript 代碼：
`onclick=JavaScript`
HTML 事件的例子：
* 當用戶點擊鼠標時
* 當網頁已加載時
* 當圖像已加載時
* 當鼠標移動到元素上時
* 當輸入字段被改變時
* 當提交 HTML 表單時
* 當用戶觸發按鍵時

在本例中，當用戶在 `<h1>` 元素上點擊時，會改變其內容：
```
<h1 onclick="this.innerHTML='謝謝!'">請點擊該文本</h1>
```

本例從事件處理器調用一個函數：
```
<!DOCTYPE html>
<html>
<head>
<script>
function changetext(id)
{
id.innerHTML="謝謝!";
}
</script>
</head>
<body>
<h1 onclick="changetext(this)">請點擊該文本</h1>
</body>
</html>
```
####HTML 事件屬性
如需向 HTML 元素分配 事件，您可以使用事件屬性。
向 button 元素分配 onclick 事件：
`<button onclick="displayDate()">點擊這裡</button>`

在上面的例子中，名為 displayDate 的函數將在按鈕被點擊時執行。
####使用 HTML DOM 來分配事件
HTML DOM 允許您通過使用 JavaScript 來向 HTML 元素分配事件：
向 button 元素分配 onclick 事件：
```
<script>
document.getElementById("myBtn").onclick=function(){displayDate()};
</script>
```
在上面的例子中，名為 displayDate 的函數被分配給 id=myButn" 的 HTML 元素。
當按鈕被點擊時，會執行該函數。
####onload 和 onunload 事件
onload 和 onunload 事件會在用戶進入或離開頁面時被觸發。
onload 事件可用於檢測訪問者的瀏覽器類型和瀏覽器版本，並基於這些信息來加載網頁的正確版本。
onload 和 onunload 事件可用於處理 cookie。
`<body onload="checkCookies()">`

####onchange 事件
onchange 事件常結合對輸入字段的驗證來使用。
下面是一個如何使用 onchange 的例子。當用戶改變輸入字段的內容時，會調用 upperCase() 函數。
`<input type="text" id="fname" onchange="upperCase()">`

####onmouseover 和 onmouseout 事件
onmouseover 和 onmouseout 事件可用於在用戶的鼠標移至 HTML 元素上方或移出元素時觸發函數。
一個簡單的 onmouseover-onmouseout 實例：
```html
<!DOCTYPE html>
<html>
<body>

<div onmouseover="mOver(this)" onmouseout="mOut(this)" style="background-color:green;width:120px;height:20px;padding:40px;color:#ffffff;">把鼠標移到上面</div>

<script>
function mOver(obj)
{
obj.innerHTML="謝謝"
}

function mOut(obj)
{
obj.innerHTML="把鼠標移到上面"
}
</script>

</body>
</html>
```
####onmousedown、onmouseup 以及 onclick 事件
onmousedown, onmouseup 以及 onclick 構成了鼠標點擊事件的所有部分。首先當點擊鼠標按鈕時，會觸發 onmousedown 事件，當釋放鼠標按鈕時，會觸發 onmouseup 事件，最後，當完成鼠標點擊時，會觸發 onclick 事件。
```html
<!DOCTYPE html>
<html>
<body>

<div onmousedown="mDown(this)" onmouseup="mUp(this)" style="background-color:green;color:#ffffff;width:90px;height:20px;padding:40px;font-size:12px;">請點擊這裡</div>

<script>
function mDown(obj)
{
obj.style.backgroundColor="#1ec5e5";
obj.innerHTML="請釋放鼠標按鈕"
}

function mUp(obj)
{
obj.style.backgroundColor="green";
obj.innerHTML="請按下鼠標按鈕"
}
</script>

</body>
</html>
```
####onfocus 事件
```html
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction(x)
{
x.style.background="yellow";
}
</script>
</head>
<body>

請輸入英文字符：<input type="text" onfocus="myFunction(this)">

<p>當輸入字段獲得焦點時，會觸發改變背景顏色的函數。</p>

</body>
</html>
```

添加和刪除節點（HTML 元素）。
####創建新的 HTML 元素
如需向 HTML DOM 添加新元素，您必須首先創建該元素（元素節點），然後向一個已存在的元素追加該元素。
```html
<div id="div1">
<p id="p1">這是一個段落</p>
<p id="p2">這是另一個段落</p>
</div>

<script>
var para=document.createElement("p");
var node=document.createTextNode("這是新段落。");
para.appendChild(node);

var element=document.getElementById("div1");
element.appendChild(para);
</script>
```
例子解釋：
這段代碼創建新的 `<p>` 元素：
`var para=document.createElement("p");`
如需向 `<p>` 元素添加文本，您必須首先創建文本節點。這段代碼創建了一個文本節點：
`var node=document.createTextNode("這是新段落。");`
然後您必須向 `<p>` 元素追加這個文本節點：
`para.appendChild(node);`
最後您必須向一個已有的元素追加這個新元素。
這段代碼找到一個已有的元素：
`var element=document.getElementById("div1");`
這段代碼向這個已有的元素追加新元素：
`element.appendChild(para);`
####刪除已有的 HTML 元素
如需刪除 HTML 元素，您必須首先獲得該元素的父元素：
```html
<div id="div1">
<p id="p1">這是一個段落。</p>
<p id="p2">這是另一個段落。</p>
</div>

<script>
var parent=document.getElementById("div1");
var child=document.getElementById("p1");
parent.removeChild(child);
</script>
```
例子解釋：
這個 HTML 文檔含有擁有兩個子節點（兩個 `<p>` 元素）的 `<div>` 元素：
```
<div id="div1">
<p id="p1">這是一個段落。</p>
<p id="p2">這是另一個段落。</p>
</div>
```
找到 id="div1" 的元素：
`var parent=document.getElementById("div1");`
找到 id="p1" 的 <p> 元素：
`var child=document.getElementById("p1");`
從父元素中刪除子元素：
`parent.removeChild(child);`
提示：如果能夠在不引用父元素的情況下刪除某個元素，就太好了。
不過很遺憾。DOM 需要清楚您需要刪除的元素，以及它的父元素。
這是常用的解決方案：找到您希望刪除的子元素，然後使用其 parentNode 屬性來找到父元素：
```
var child=document.getElementById("p1");
child.parentNode.removeChild(child);
```