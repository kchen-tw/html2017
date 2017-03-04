HTML表格  
表格由 &lt;table&gt; 標籤來定義。每個表格均有若干行（由 &lt;tr&gt; 標籤定義），每行被分割為若干單元格（由 &lt;td&gt; 標籤定義）。字母 td 指表格數據（table data），即數據單元格的內容。數據單元格可以包含文本、圖片、列表、段落、表單、水平線、表格等等。

&lt;table border="1"&gt;  
&lt;tr&gt;  
&lt;td&gt;row 1, cell 1&lt;/td&gt;  
&lt;td&gt;row 1, cell 2&lt;/td&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
&lt;td&gt;row 2, cell 1&lt;/td&gt;  
&lt;td&gt;row 2, cell 2&lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;  
表格和邊框屬性  
如果不定義邊框屬性，表格將不顯示邊框。有時這很有用，但是大多數時候，我們希望顯示邊框。 使用邊框屬性來顯示一個帶有邊框的表格：

&lt;table border="1"&gt;  
&lt;tr&gt;  
&lt;td&gt;Row 1, cell 1&lt;/td&gt;  
&lt;td&gt;Row 1, cell 2&lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;  
表格的表頭  
表格的表頭使用 &lt;th&gt; 標籤進行定義。 大多數瀏覽器會把表頭顯示為粗體居中的文本：

&lt;table border="1"&gt;  
&lt;tr&gt;  
&lt;th&gt;Heading&lt;/th&gt;  
&lt;th&gt;Another Heading&lt;/th&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
&lt;td&gt;row 1, cell 1&lt;/td&gt;  
&lt;td&gt;row 1, cell 2&lt;/td&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
&lt;td&gt;row 2, cell 1&lt;/td&gt;  
&lt;td&gt;row 2, cell 2&lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;

跨行或跨列的表格

&lt;h4&gt;橫跨兩列的單元格：&lt;/h4&gt;  
&lt;table border="1"&gt;  
&lt;tr&gt;  
  &lt;th&gt;姓名&lt;/th&gt;  
  &lt;th colspan="2"&gt;電話&lt;/th&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
  &lt;td&gt;Bill Gates&lt;/td&gt;  
  &lt;td&gt;555 77 854&lt;/td&gt;  
  &lt;td&gt;555 77 855&lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;

&lt;h4&gt;橫跨兩行的單元格：&lt;/h4&gt;  
&lt;table border="1"&gt;  
&lt;tr&gt;  
  &lt;th&gt;姓名&lt;/th&gt;  
  &lt;td&gt;Bill Gates&lt;/td&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
  &lt;th rowspan="2"&gt;電話&lt;/th&gt;  
  &lt;td&gt;555 77 854&lt;/td&gt;  
&lt;/tr&gt;  
&lt;tr&gt;  
  &lt;td&gt;555 77 855&lt;/td&gt;  
&lt;/tr&gt;  
&lt;/table&gt;



