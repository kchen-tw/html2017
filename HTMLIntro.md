# HTML 介紹

```html
<!DOCTYPE html>
<html>
<head>
<title>Page Title</title>
</head>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

## HTML 標題

HTML 標題（Heading）是通過 &lt;h1&gt; ~ &lt;h6&gt; 等標籤進行定義的。  
`<h1>This is a heading</h1>`

`<h2>This is a heading</h2>`

`<h3>This is a heading</h3>`

## HTML 段落

HTML 段落是通過 &lt;p&gt; 標籤進行定義的。  
`<p>This is a paragraph.</p>`

## HTML 链接

HTML 鏈接是通過 &lt;a&gt; 標籤進行定義的。  
`<a href="http://www.w3school.com.cn">This is a link</a>`

## HTML 图像

HTML 圖像是通過 &lt;img&gt; 標籤進行定義的。  
`<img src="w3school.jpg" width="104" height="142" />`

## HTML 水平线

&lt;hr /&gt; 標籤在 HTML 頁面中創建水平線。  
hr 元素可用於分隔內容。

`<p>This is a paragraph</p>  
<hr />`
## HTML 樣式實例 - 背景顏色
background-color 屬性為元素定義了背景顏色：
```html
<body style="background-color:yellow">
<h2 style="background-color:red">This is a heading</h2>
<p style="background-color:green">This is a paragraph.</p>
</body>
```
## HTML 樣式實例 - 字體、顏色和尺寸
font-family、color 以及 font-size 屬性分別定義元素中文本的字體系列、顏色和字體尺寸：
```html
<body>
<h1 style="font-family:verdana">A heading</h1>
<p style="font-family:arial;color:red;font-size:20px;">A paragraph.</p>
</body>
```
## HTML 樣式實例 - 文本對齊
text-align 屬性規定了元素中文本的水平對齊方式：
```html
<body>
<h1 style="text-align:center">This is a heading</h1>
<p>The heading above is aligned to the center of this page.</p>
</body>
```
## 文本格式化標籤
```html
<b>粗體</b>
<i>斜體</i>
<sub>下標</sub>
<sup>上標</sup>
<code>程式碼</code>
<q>短區塊引用</q>
<blockquote>長區塊引用</blockquote>
<pre>pre會保留你輸入的所有空格和斷行</pre>
```
## HTML 注釋標籤
您能夠通過如下語法向 HTML 源代碼添加註釋：
`<!-- 在此處寫注釋 -->`
```<!--
可一次注釋多行
-->```
## HTML圖像標籤（img）和源屬性（Src）
在 HTML 中，圖像由 `<img>` 標籤定義。
`<img>` 是空標籤，意思是說，它只包含屬性，並且沒有閉合標籤。
要在頁面上顯示圖像，你需要使用源屬性（src）。src 指 "source"。源屬性的值是圖像的 URL 地址。
定義圖像的語法是：
`<img src="www.w3school.com.cn" />`
### 替換文本屬性（Alt）
alt 屬性用來為圖像定義一串預備的可替換的文本。
`<img src="boat.gif" alt="Big Boat">`
## HTML表格
表格由 `<table>` 標籤來定義。每個表格均有若干行（由 `<tr>` 標籤定義），每行被分割為若干單元格（由 `<td>` 標籤定義）。字母 td 指表格數據（table data），即數據單元格的內容。數據單元格可以包含文本、圖片、列表、段落、表單、水平線、表格等等。
```html
<table border="1">
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>row 2, cell 1</td>
<td>row 2, cell 2</td>
</tr>
</table>
```
### 表格和邊框屬性
如果不定義邊框屬性，表格將不顯示邊框。有時這很有用，但是大多數時候，我們希望顯示邊框。
使用邊框屬性來顯示一個帶有邊框的表格：
```html
<table border="1">
<tr>
<td>Row 1, cell 1</td>
<td>Row 1, cell 2</td>
</tr>
</table>
```
### 表格的表頭
表格的表頭使用 `<th>` 標籤進行定義。
大多數瀏覽器會把表頭顯示為粗體居中的文本：
```html
<table border="1">
<tr>
<th>Heading</th>
<th>Another Heading</th>
</tr>
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
</tr>
<tr>
<td>row 2, cell 1</td>
<td>row 2, cell 2</td>
</tr>
</table>
```
## 無序列表
無序列表是一個項目的列表，此列項目使用粗體圓點（典型的小黑圓圈）進行標記。
無序列表始於 `<ul>` 標籤。每個列表項始於 `<li>`。
```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```
## 有序列表
同樣，有序列表也是一列項目，列表項目使用數字進行標記。
有序列表始於 `<ol>` 標籤。每個列表項始於 `<li>` 標籤。
```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```
## 定義列表
自定義列表不僅僅是一列項目，而是項目及其注釋的組合。
自定義列表以 `<dl>` 標籤開始。每個自定義列表項以 `<dt>` 開始。每個自定義列表項的定義以 `<dd>` 開始。
```html
<dl>
<dt>Coffee</dt>
<dd>Black hot drink</dd>
<dt>Milk</dt>
<dd>White cold drink</dd>
</dl>
```
列表項內部可以使用段落、換行符、圖片、鏈接以及其他列表等等。





