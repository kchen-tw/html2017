### 使用 `<div>` 元素的 HTML 佈局
注釋：`<div>` 元素常用作佈局工具，因為能夠輕鬆地通過 CSS 對其進行定位。 這個例子使用了四個 `<div>` 元素來創建多列佈局：
```html
<body>
<div id="header"> <h1>City Gallery</h1> </div>
<div id="nav"> London<br> Paris<br> Tokyo<br> </div>
<div id="section"> <h1>London</h1>
<p> London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants. </p> <p> Standing on the River Thames, London has been a major settlement for two millennia, its history going back to its founding by the Romans, who named it Londinium. </p> </div>
<div id="footer"> Copyright W3School.com.cn </div>
</body>

```
<body>
<div id="header"> <h1>City Gallery</h1> </div>
<div id="nav"> London<br> Paris<br> Tokyo<br> </div>
<div id="section"> <h1>London</h1>
<p> London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants. </p> <p> Standing on the River Thames, London has been a major settlement for two millennia, its history going back to its founding by the Romans, who named it Londinium. </p> </div>
<div id="footer"> Copyright W3School.com.cn </div>
</body>

### 使用 HTML5 的網站佈局
HTML5 提供的新語義元素定義了網頁的不同部分： HTML5 語義元素 header 定義文檔或節的頁眉 nav 定義導航鏈接的容器 section 定義文檔中的節 article 定義獨立的自包含文章 aside 定義內容之外的內容（比如側欄） footer 定義文檔或節的頁腳 details 定義額外的細節 summary 定義 details 元素的標題 這個例子使用 `<header>`, `<nav>`, `<section>`, 以及 `<footer>` 來創建多列佈局：
```html
<body>
<header> <h1>City Gallery</h1> </header>
<nav> London<br> Paris<br> Tokyo<br> </nav>
<section> <h1>London</h1> <p> London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants. </p> <p> Standing on the River Thames, London has been a major settlement for two millennia, its history going back to its founding by the Romans, who named it Londinium. </p> </section>
<footer> Copyright W3School.com.cn </footer>
</body>

```
<body>
<header> <h1>City Gallery</h1> </header>
<nav> London<br> Paris<br> Tokyo<br> </nav>
<section> <h1>London</h1> <p> London is the capital city of England. It is the most populous city in the United Kingdom, with a metropolitan area of over 13 million inhabitants. </p> <p> Standing on the River Thames, London has been a major settlement for two millennia, its history going back to its founding by the Romans, who named it Londinium. </p> </section>
<footer> Copyright W3School.com.cn </footer>
</body>

### 使用表格的 HTML 佈局
注釋：<table> 元素不是作為佈局工具而設計的。 <table> 元素的作用是顯示表格化的數據。 使用 <table> 元素能夠取得佈局效果，因為能夠通過 CSS 設置表格元素的樣式：
```html
<body>
<table class="lamp"> <tr> <th> <img src="http://www.w3school.com.cn/images/lamp.jpg" alt="Note" style="height:32px;width:32px"> </th> <td> The table element was not designed to be a layout tool. </td> </tr> </table>
</body>
```
<body>
<table class="lamp"> <tr> <th> <img src="http://www.w3school.com.cn/images/lamp.jpg" alt="Note" style="height:32px;width:32px"> </th> <td> The table element was not designed to be a layout tool. </td> </tr> </table>
</body>
