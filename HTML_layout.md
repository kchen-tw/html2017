使用 &lt;div&gt; 元素的 HTML 佈局  
注釋：&lt;div&gt; 元素常用作佈局工具，因為能夠輕鬆地通過 CSS 對其進行定位。  
這個例子使用了四個 &lt;div&gt; 元素來創建多列佈局：  
實例  
&lt;body&gt;  
  
&lt;div id="header"&gt;  
&lt;h1&gt;City Gallery&lt;/h1&gt;  
&lt;/div&gt;  
  
&lt;div id="nav"&gt;  
London&lt;br&gt;  
Paris&lt;br&gt;  
Tokyo&lt;br&gt;  
&lt;/div&gt;  
  
&lt;div id="section"&gt;  
&lt;h1&gt;London&lt;/h1&gt;  
&lt;p&gt;  
London is the capital city of England. It is the most populous city in the United Kingdom,  
with a metropolitan area of over 13 million inhabitants.  
&lt;/p&gt;  
&lt;p&gt;  
Standing on the River Thames, London has been a major settlement for two millennia,  
its history going back to its founding by the Romans, who named it Londinium.  
&lt;/p&gt;  
&lt;/div&gt;  
  
&lt;div id="footer"&gt;  
Copyright W3School.com.cn  
&lt;/div&gt;  
  
&lt;/body&gt;  
CSS：  
&lt;style&gt;  
\#header {  
    background-color:black;  
    color:white;  
    text-align:center;  
    padding:5px;  
}  
\#nav {  
    line-height:30px;  
    background-color:\#eeeeee;  
    height:300px;  
    width:100px;  
    float:left;  
    padding:5px;   
}  
\#section {  
    width:350px;  
    float:left;  
    padding:10px;   
}  
\#footer {  
    background-color:black;  
    color:white;  
    clear:both;  
    text-align:center;  
    padding:5px;   
}  
&lt;/style&gt;  
  
使用 HTML5 的網站佈局  
HTML5 提供的新語義元素定義了網頁的不同部分：  
HTML5 語義元素  
header	定義文檔或節的頁眉  
nav	定義導航鏈接的容器  
section	定義文檔中的節  
article	定義獨立的自包含文章  
aside	定義內容之外的內容（比如側欄）  
footer	定義文檔或節的頁腳  
details	定義額外的細節  
summary	定義 details 元素的標題  
這個例子使用 &lt;header&gt;, &lt;nav&gt;, &lt;section&gt;, 以及 &lt;footer&gt; 來創建多列佈局：  
實例  
&lt;body&gt;  
  
&lt;header&gt;  
&lt;h1&gt;City Gallery&lt;/h1&gt;  
&lt;/header&gt;  
  
&lt;nav&gt;  
London&lt;br&gt;  
Paris&lt;br&gt;  
Tokyo&lt;br&gt;  
&lt;/nav&gt;  
  
&lt;section&gt;  
&lt;h1&gt;London&lt;/h1&gt;  
&lt;p&gt;  
London is the capital city of England. It is the most populous city in the United Kingdom,  
with a metropolitan area of over 13 million inhabitants.  
&lt;/p&gt;  
&lt;p&gt;  
Standing on the River Thames, London has been a major settlement for two millennia,  
its history going back to its founding by the Romans, who named it Londinium.  
&lt;/p&gt;  
&lt;/section&gt;  
  
&lt;footer&gt;  
Copyright W3School.com.cn  
&lt;/footer&gt;  
  
&lt;/body&gt;  
  
CSS  
&lt;style&gt;  
header {  
    background-color:black;  
    color:white;  
    text-align:center;  
    padding:5px;   
}  
nav {  
    line-height:30px;  
    background-color:\#eeeeee;  
    height:300px;  
    width:100px;  
    float:left;  
    padding:5px;   
}  
section {  
    width:350px;  
    float:left;  
    padding:10px;   
}  
footer {  
    background-color:black;  
    color:white;  
    clear:both;  
    text-align:center;  
    padding:5px;   
}  
  
使用表格的 HTML 佈局  
注釋：&lt;table&gt; 元素不是作為佈局工具而設計的。  
&lt;table&gt; 元素的作用是顯示表格化的數據。  
使用 &lt;table&gt; 元素能夠取得佈局效果，因為能夠通過 CSS 設置表格元素的樣式：  
實例  
&lt;body&gt;  
  
&lt;table class="lamp"&gt;  
&lt;tr&gt;  
  &lt;th&gt;  
    &lt;img src="/images/lamp.jpg" alt="Note" style="height:32px;width:32px"&gt;  
  &lt;/th&gt;  
  &lt;td&gt;  
    The table element was not designed to be a layout tool.  
  &lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;  
  
&lt;/body&gt;  
  
CSS  
&lt;style&gt;  
table.lamp {  
    width:100%;  
    border:1px solid \#d4d4d4;  
}  
table.lamp th, td {  
    padding:10px;  
}  
table.lamp td {  
    width:40px;  
}  
&lt;/style&gt;

