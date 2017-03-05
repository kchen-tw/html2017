### HTML表格
表格由 `<table>` 標籤來定義。每個表格均有若干行（由 `<tr>` 標籤定義），每行被分割為若干單元格（由 `<td>` 標籤定義）。字母 td 指表格數據（table data），即數據單元格的內容。數據單元格可以包含文本、圖片、列表、段落、表單、水平線、表格等等。
```html
<table border="1">
<tr> <td>row 1, cell 1</td> <td>row 1, cell 2</td></tr>
<tr> <td>row 2, cell 1</td> <td>row 2, cell 2</td> </tr>
</table>
```

<table border="1"><tr> <td>row 1, cell 1</td> <td>row 1, cell 2</td></tr><tr> <td>row 2, cell 1</td> <td>row 2, cell 2</td> </tr></table>
表格和邊框屬性 如果不定義邊框屬性，表格將不顯示邊框。有時這很有用，但是大多數時候，我們希望顯示邊框。

#### 表格的表頭
表格的表頭使用 `<th>` 標籤進行定義。 大多數瀏覽器會把表頭顯示為粗體居中的文本：
```html
<table border="1">
<tr> <th>Heading</th> <th>Another Heading</th> </tr>
<tr> <td>row 1, cell 1</td> <td>row 1, cell 2</td> </tr>
<tr> <td>row 2, cell 1</td> <td>row 2, cell 2</td> </tr>
</table>
```
<table border="1"> <tr> <th>Heading</th> <th>Another Heading</th> </tr> <tr> <td>row 1, cell 1</td> <td>row 1, cell 2</td> </tr> <tr> <td>row 2, cell 1</td> <td>row 2, cell 2</td> </tr> </table>


#### 跨行或跨列的表格
```html
<h4>橫跨兩列的單元格：</h4>
<table border="1">
<tr> <th>姓名</th> <th colspan="2">電話</th> </tr>
<tr> <td>Bill Gates</td> <td>555 77 854</td> <td>555 77 855</td> </tr>
</table>

<h4>橫跨兩行的單元格：</h4>
<table border="1">
<tr> <th>姓名</th> <td>Bill Gates</td></tr>
<tr> <th rowspan="2">電話</th> <td>555 77 854</td> </tr>
<tr> <td>555 77 855</td> </tr>
</table>
```