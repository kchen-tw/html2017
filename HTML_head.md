### HTML`<head>` 元素是所有頭部元素的容器。
`<head>` 內的元素可包含腳本，指示瀏覽器在何處可以找到樣式表，提供元信息，等等。 以下標籤都可以添加到 head 部分： `<title>`、`<base>`、`<link>`、`<meta>`、`<script>` 以及 `<style>`。 

### HTML `<title>` 元素
`<title>` 標籤定義文檔的標題。 title 元素在所有 HTML/XHTML 文檔中都是必需的。 title 元素能夠： 定義瀏覽器工具欄中的標題 提供頁面被添加到收藏夾時顯示的標題顯示在搜索引擎結果中的頁面標題。

### HTML `<base>` 元素
`<base>` 標籤為頁面上的所有鏈接規定默認地址或默認目標（target）： 
```html
<head> <base href="http://www.w3school.com.cn/images/" /> <base target="_blank" /> </head>
```

### HTML <link> 元素
`<link>` 標籤定義文檔與外部資源之間的關係。 `<link>` 標籤最常用於連接樣式表：
```html
<head> <link rel="stylesheet" type="text/css" href="mystyle.css" /> </head>
``` 

###HTML `<style>` 元素
`<style>` 標籤用於為 HTML 文檔定義樣式信息。 您可以在 style 元素內規定 HTML 元素在瀏覽器中呈現的樣式：
```html
<head> <style type="text/css"> body {background-color:yellow} p {color:blue} </style> </head>
```
### HTML <meta> 元素
元數據（metadata）是關於數據的信息。 `<meta>` 標籤提供關於 HTML 文檔的元數據。元數據不會顯示在頁面上，但是對於機器是可讀的。 典型的情況是，meta 元素被用於規定頁面的描述、關鍵詞、文檔的作者、最後修改時間以及其他元數據。 `<meta>` 標籤始終位於 head 元素中。 元數據可用於瀏覽器（如何顯示內容或重新加載頁面），搜索引擎（關鍵詞），或其他 web 服務。 針對搜索引擎的關鍵詞 一些搜索引擎會利用 meta 元素的 name 和 content 屬性來索引您的頁面。 下面的 meta 元素定義頁面的描述：`<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />` 下面的 meta 元素定義頁面的關鍵詞： `<meta name="keywords" content="HTML, CSS, XML" />` name 和 content 屬性的作用是描述頁面的內容。

###HTML <script> 元素
`<script>` 標籤用於定義客戶端腳本，比如 JavaScript。 我們會在稍後的章節講解 script 元素。