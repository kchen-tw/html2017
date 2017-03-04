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

### 如何使用樣式

當瀏覽器讀到一個樣式表，它就會按照這個樣式表來對文檔進行格式化。有以下三種方式來插入樣式表：

#### 外部樣式表

當樣式需要被應用到很多頁面的時候，外部樣式表將是理想的選擇。使用外部樣式表，你就可以通過更改一個文件來改變整個站點的外觀。  
&lt;head&gt;  
&lt;link rel="stylesheet" type="text/css" href="mystyle.css"&gt;  
&lt;/head&gt;

#### 內部樣式表

當單個文件需要特別樣式時，就可以使用內部樣式表。你可以在 head 部分通過 &lt;style&gt; 標籤定義內部樣式表。  
&lt;head&gt;  
&lt;style type="text/css"&gt;  
body {background-color: red}  
p {margin-left: 20px}  
&lt;/style&gt;  
&lt;/head&gt;

#### 內聯樣式

當特殊的樣式需要應用到個別元素時，就可以使用內聯樣式。 使用內聯樣式的方法是在相關的標籤中使用樣式屬性。樣式屬性可以包含任何 CSS 屬性。以下實例顯示出如何改變段落的顏色和左外邊距。  
&lt;p style="color: red; margin-left: 20px"&gt;  
This is a paragraph  
&lt;/p&gt;

