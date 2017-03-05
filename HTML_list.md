### 無序列表
無序列表是一個項目的列表，此列項目使用粗體圓點（典型的小黑圓圈）進行標記。 無序列表始於 `<ul>` 標籤。每個列表項始於 `<li>`。
```html
<ul> <li>Coffee</li> <li>Milk</li> </ul>
```
<ul> <li>Coffee</li> <li>Milk</li> </ul>

### 有序列表
同樣，有序列表也是一列項目，列表項目使用數字進行標記。 有序列表始於 `<ol>` 標籤。每個列表項始於 `<li>` 標籤。
```html
<ol> <li>Coffee</li> <li>Milk</li> </ol>
```
<ol> <li>Coffee</li> <li>Milk</li> </ol>

### 定義列表
自定義列表不僅僅是一列項目，而是項目及其注釋的組合。 自定義列表以 `<dl>` 標籤開始。每個自定義列表項以 `<dt>` 開始。每個自定義列表項的定義以 `<dd>` 開始。
```html
<dl> <dt>Coffee</dt> <dd>Black hot drink</dd> <dt>Milk</dt> <dd>White cold drink</dd> </dl>
```
<dl>
 <dt>Coffee</dt>
  <dd>Black hot drink</dd>
 <dt>Milk</dt>
  <dd>White cold drink</dd>
</dl>
列表項內部可以使用段落、換行符、圖片、鏈接以及其他列表等等。

### 使用不同類型的列表
```html
<h4>數字列表：</h4> <ol> <li>蘋果</li> <li>香蕉</li> <li>檸檬</li> <li>桔子</li> </ol>

<h4>字母列表：</h4> <ol type="A"> <li>蘋果</li> <li>香蕉</li> <li>檸檬</li> <li>桔子</li> </ol>

<h4>小寫字母列表：</h4> <ol type="a"> <li>蘋果</li> <li>香蕉</li> <li>檸檬</li> <li>桔子</li> </ol>

<h4>羅馬字母列表：</h4> <ol type="I"> <li>蘋果</li> <li>香蕉</li> <li>檸檬</li> <li>桔子</li> </ol>

<h4>小寫羅馬字母列表：</h4> <ol type="i"> <li>蘋果</li> <li>香蕉</li> <li>檸檬</li> <li>桔子</li> </ol>
```