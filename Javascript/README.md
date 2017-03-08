HTML 中的腳本必須位於 `<script>` 與 `</script>` 標籤之間。
腳本可被放置在 HTML 頁面的 `<body>` 和 `<head>` 部分中。

###`<script>` 標籤
如需在 HTML 頁面中插入 JavaScript，請使用 `<script>` 標籤。
`<script>` 和 `</script>` 會告訴 JavaScript 在何處開始和結束。
`<script>` 和 `</script>` 之間的代碼行包含了 JavaScript：
```
<script>
alert("My First JavaScript");
</script>
```
您無需理解上面的代碼。只需明白，瀏覽器會解釋並執行位於 `<script>` 和 `</script>` 之間的 JavaScript。
那些老舊的實例可能會在 `<script>` 標籤中使用 type="text/javascript"。現在已經不必這樣做了。JavaScript 是所有現代瀏覽器以及 HTML5 中的默認腳本語言。
`<body>` 中的 JavaScript
在本例中，JavaScript 會在頁面加載時向 HTML 的 <body> 寫文本：
```html
<!DOCTYPE html>
<html>
<body>
.
.
<script>
document.write("<h1>This is a heading</h1>");
document.write("<p>This is a paragraph</p>");
</script>
.
.
</body>
</html>
```

###JavaScript 函數和事件
上面例子中的 JavaScript 語句，會在頁面加載時執行。
通常，我們需要在某個事件發生時執行代碼，比如當用戶點擊按鈕時。
如果我們把 JavaScript 代碼放入函數中，就可以在事件發生時調用該函數。
您將在稍後的章節學到更多有關 JavaScript 函數和事件的知識。
`<head>` 或 `<body>` 中的 JavaScript
您可以在 HTML 文檔中放入不限數量的腳本。
腳本可位於 HTML 的 `<body>` 或 `<head>` 部分中，或者同時存在於兩個部分中。
通常的做法是把函數放入 `<head>` 部分中，或者放在頁面底部。這樣就可以把它們安置到同一處位置，不會干擾頁面的內容。
`<head>` 中的 JavaScript 函數
在本例中，我們把一個 JavaScript 函數放置到 HTML 頁面的 <head> 部分。
該函數會在點擊按鈕時被調用：
```html
<!DOCTYPE html>
<html>

<head>
<script>
function myFunction()
{
document.getElementById("demo").innerHTML="My First JavaScript Function";
}
</script>
</head>

<body>

<h1>My Web Page</h1>

<p id="demo">A Paragraph</p>

<button type="button" onclick="myFunction()">Try it</button>

</body>
</html>
```

###`<body>` 中的 JavaScript 函數
在本例中，我們把一個 JavaScript 函數放置到 HTML 頁面的 <body> 部分。
該函數會在點擊按鈕時被調用：
```html
<!DOCTYPE html>
<html>
<body>

<h1>My Web Page</h1>

<p id="demo">A Paragraph</p>

<button type="button" onclick="myFunction()">Try it</button>

<script>
function myFunction()
{
document.getElementById("demo").innerHTML="My First JavaScript Function";
}
</script>

</body>
</html>
```
提示：我們把 JavaScript 放到了頁面代碼的底部，這樣就可以確保在 `<p>` 元素創建之後再執行腳本。

###外部的 JavaScript
也可以把腳本保存到外部文件中。外部文件通常包含被多個網頁使用的代碼。
外部 JavaScript 文件的文件擴展名是 .js。
如需使用外部文件，請在 `<script>` 標籤的 "src" 屬性中設置該 .js 文件：
```html
<!DOCTYPE html>
<html>
<body>
<script src="myScript.js"></script>
</body>
</html>
```
在 `<head>` 或 `<body>` 中引用腳本文件都是可以的。實際運行效果與您在 `<script>` 標籤中編寫腳本完全一致。
提示：外部腳本不能包含 `<script>` 標籤。