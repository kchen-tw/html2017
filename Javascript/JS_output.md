JavaScript 通常用於操作 HTML 元素。
##操作 HTML 元素
如需從 JavaScript 訪問某個 HTML 元素，您可以使用 document.getElementById(id) 方法。
請使用 "id" 屬性來標識 HTML 元素：

通過指定的 id 來訪問 HTML 元素，並改變其內容：
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>

<p id="demo">My First Paragraph</p>

<script>
document.getElementById("demo").innerHTML="My First JavaScript";
</script>

</body>
</html>
```
JavaScript 由 web 瀏覽器來執行。在這種情況下，瀏覽器將訪問 id="demo" 的 HTML 元素，並把它的內容（innerHTML）替換為 "My First JavaScript"。
寫到文檔輸出
下面的例子直接把 <p> 元素寫到 HTML 文檔輸出中：
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>

<script>
document.write("<p>My First JavaScript</p>");
</script>

</body>
</html>
```
警告
請使用 document.write() 僅僅向文檔輸出寫內容。
如果在文檔已完成加載後執行 document.write，整個 HTML 頁面將被覆蓋：
```html
<!DOCTYPE html>
<html>
<body>

<h1>My First Web Page</h1>

<p>My First Paragraph.</p>

<button onclick="myFunction()">點擊這裡</button>

<script>
function myFunction()
{
document.write("糟糕！文檔消失了。");
}
</script>

</body>
</html>
```