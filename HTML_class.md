對 HTML 進行分類（設置類），使我們能夠為元素的類定義 CSS 樣式。  
為相同的類設置相同的樣式，或者為不同的類設置不同的樣式。  
分類塊級元素  
HTML &lt;div&gt; 元素是塊級元素。它能夠用作其他 HTML 元素的容器。  
設置 &lt;div&gt; 元素的類，使我們能夠為相同的 &lt;div&gt; 元素設置相同的類：  
&lt;!DOCTYPE html&gt;  
&lt;html&gt;  
&lt;head&gt;  
&lt;style&gt;  
.cities {  
    background-color:black;  
    color:white;  
    margin:20px;  
    padding:20px;  
}   
&lt;/style&gt;  
&lt;/head&gt;  
  
&lt;body&gt;  
  
&lt;div class="cities"&gt;  
&lt;h2&gt;London&lt;/h2&gt;  
&lt;p&gt;  
London is the capital city of England.   
It is the most populous city in the United Kingdom,   
with a metropolitan area of over 13 million inhabitants.  
&lt;/p&gt;  
&lt;/div&gt;   
  
&lt;/body&gt;  
&lt;/html&gt;  
分類行內元素  
HTML &lt;span&gt; 元素是行內元素，能夠用作文本的容器。  
設置 &lt;span&gt; 元素的類，能夠為相同的 &lt;span&gt; 元素設置相同的樣式。  
&lt;!DOCTYPE html&gt;  
&lt;html&gt;  
&lt;head&gt;  
&lt;style&gt;  
  span.red {color:red;}  
&lt;/style&gt;  
&lt;/head&gt;  
&lt;body&gt;  
  
&lt;h1&gt;My &lt;span class="red"&gt;Important&lt;/span&gt; Heading&lt;/h1&gt;  
  
&lt;/body&gt;  
&lt;/html&gt;

