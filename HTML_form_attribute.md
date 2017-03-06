## HTML Input 屬性
### value 屬性
value 屬性規定輸入字段的初始值：
```html
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```
 
###readonly 屬性
readonly 屬性規定輸入字段為只讀（不能修改）：
```html
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" readonly>
<br>
 Last name:<br>
<input type="text" name="lastname">
</form>
 ```
readonly 屬性不需要值。它等同於 readonly="readonly"。

###disabled 屬性
disabled 屬性規定輸入字段是禁用的。
被禁用的元素是不可用和不可點擊的。
被禁用的元素不會被提交。
```html
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" disabled>
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
 ```
disabled 屬性不需要值。它等同於 disabled="disabled"。

###size 屬性
size 屬性規定輸入字段的尺寸（以字符計）：
```html
<form action="">
 First name:<br>
<input type="text" name="firstname" value="John" size="40">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```
   
###maxlength 屬性
maxlength 屬性規定輸入字段允許的最大長度：
```html
<form action="">
 First name:<br>
<input type="text" name="firstname" maxlength="10">
<br>
 Last name:<br>
<input type="text" name="lastname">
</form> 
```
   
###HTML5 屬性
HTML5 為 `<input>` 增加了如下屬性：
autocomplete
autofocus
form
formaction
formenctype
formmethod
formnovalidate
formtarget
height 和 width
list
min 和 max
multiple
pattern (regexp)
placeholder
required
step
並為 `<form>` 增加如需屬性：
autocomplete
novalidate

###autocomplete 屬性
autocomplete 屬性規定表單或輸入字段是否應該自動完成。
當自動完成開啓，瀏覽器會基於用戶之前的輸入值自動填寫值。
提示：
Tip: It is possible to have autocomplete "on" for the form、and "off" for specific input fields、or vice versa.
autocomplete 屬性適用於 `<form>` 以及如下 `<input>` 類型：text、search、url、tel、email、password、datepickers、range 以及 color。

自動完成開啓的 HTML 表單（某個輸入字段為 off）：
   ```html
<form action="action_page.php" autocomplete="on">
   First name:<input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   E-mail: <input type="email" name="email" autocomplete="off"><br>
   <input type="submit">
</form> 
```
   
###novalidate 屬性
novalidate 屬性屬於 `<form>` 屬性。
如果設置，則 novalidate 規定在提交表單時不對表單數據進行驗證。
   
指示表單在被提交時不進行驗證：
   ```html
<form action="action_page.php" novalidate>
   E-mail: <input type="email" name="user_email">
   <input type="submit">
</form> 
```
   
###autofocus 屬性
autofocus 屬性是`bool`屬性。
如果設置，則規定當頁面加載時 `<input>` 元素應該自動獲得焦點。

使 "First name" 輸入字段在頁面加載時自動獲得焦點：
   ```html
First name:<input type="text" name="fname" autofocus>
```
   
###form 屬性
form 屬性規定 `<input>` 元素所屬的一個或多個表單。
提示：如需引用一個以上的表單，請使用空格分隔的表單 id 列表。

輸入字段位於 HTML 表單之外（但仍屬表單）：
   ```html
<form action="action_page.php" id="form1">
   First name: <input type="text" name="fname"><br>
   <input type="submit" value="Submit">
</form>

 Last name: <input type="text" name="lname" form="form1">
 ```
 ###formaction 屬性
formaction 屬性規定當提交表單時處理該輸入控件的文件的 URL。
formaction 屬性覆蓋 `<form>` 元素的 action 屬性。
formaction 屬性適用於 type="submit" 以及 type="image"。

擁有兩個兩個提交按鈕並對於不同動作的 HTML 表單：
```html
   <form action="action_page.php">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit"><br>
   <input type="submit" formaction="demo_admin.asp"
   value="Submit as admin">
</form> 
```

###formenctype 屬性
formenctype 屬性規定當把表單數據（form-data）提交至服務器時如何對其進行編碼（僅針對 method="post" 的表單）。
formenctype 屬性覆蓋 `<form>` 元素的 enctype 屬性。
formenctype 屬性適用於 type="submit" 以及 type="image"。

發送默認編碼以及編碼為 "multipart/form-data"（第二個提交按鈕）的表單數據（form-data）：
   ```html
<form action="demo_post_enctype.asp" method="post">
   First name: <input type="text" name="fname"><br>
   <input type="submit" value="Submit">
   <input type="submit" formenctype="multipart/form-data"
   value="Submit as Multipart/form-data">
</form> 
```
   
###formmethod 屬性
formmethod 屬性定義用以向 action URL 發送表單數據（form-data）的 HTTP 方法。
formmethod 屬性覆蓋 `<form>` 元素的 method 屬性。
formmethod 屬性適用於 type="submit" 以及 type="image"。

第二個提交按鈕覆蓋表單的 HTTP 方法：
```html
   <form action="action_page.php" method="get">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit">
   <input type="submit" formmethod="post" formaction="demo_post.asp"
   value="Submit using POST">
</form> 
```
   
###formnovalidate 屬性
formnovalidate 屬性是`bool`屬性。
如果設置，則規定在提交表單時不對 `<input>` 元素進行驗證。
formnovalidate 屬性覆蓋 `<form>` 元素的 novalidate 屬性。
formnovalidate 屬性可用於 type="submit"。

擁有兩個提交按鈕的表單（驗證和不驗證）：
   ```html
<form action="action_page.php">
   E-mail: <input type="email" name="userid"><br>
   <input type="submit" value="Submit"><br>
   <input type="submit" formnovalidate value="Submit without validation">
</form> 
```
   
###formtarget 屬性
formtarget 屬性規定的名稱或關鍵詞指示提交表單後在何處顯示接收到的響應。
formtarget 屬性會覆蓋 `<form>` 元素的 target 屬性。
formtarget 屬性可與 type="submit" 和 type="image" 使用。

這個表單有兩個提交按鈕，對應不同的目標窗口：
```html
   <form action="action_page.php">
   First name: <input type="text" name="fname"><br>
   Last name: <input type="text" name="lname"><br>
   <input type="submit" value="Submit as normal">
   <input type="submit" formtarget="_blank"
   value="Submit to a new window">
</form> 
```
   
###height 和 width 屬性
height 和 width 屬性規定 `<input>` 元素的高度和寬度。
height 和 width 屬性僅用於 `<input type="image">`。
注釋：請始終規定圖像的尺寸。如果瀏覽器不清楚圖像尺寸，則頁面會在圖像加載時閃爍。

把圖像定義為提交按鈕，並設置 height 和 width 屬性：
````html
   <input type="image" src="img_submit.gif" alt="Submit" width="48" height="48">
```
   
###list 屬性
list 屬性引用的 `<datalist>` 元素中包含了 `<input>` 元素的預定義選項。

使用 `<datalist>` 設置預定義值的 `<input>` 元素：
```html
<input list="browsers">

<datalist id="browsers">
   <option value="Internet Explorer">
   <option value="Firefox">
   <option value="Chrome">
   <option value="Opera">
   <option value="Safari">
</datalist> 
```
 Note: The datalist tag is not supported in Internet Explorer 9 and earlier versions, or in Safari.

### min 和 max 屬性
min 和 max 屬性規定 `<input>` 元素的最小值和最大值。
min 和 max 屬性適用於如需輸入類型：number、range、date、datetime、datetime-local、month、time 以及 week。

具有最小和最大值的 `<input>` 元素：
```html
 Enter a date before 1980-01-01:
<input type="date" name="bday" max="1979-12-31">

 Enter a date after 2000-01-01:
<input type="date" name="bday" min="2000-01-02">

 Quantity (between 1 and 5):
<input type="number" name="quantity" min="1" max="5">
```
 
###multiple 屬性
multiple 屬性是`bool`屬性。
如果設置，則規定允許用戶在 `<input>` 元素中輸入一個以上的值。
multiple 屬性適用於以下輸入類型：email 和 file。

接受多個值的文件上傳字段：
```html
 Select images: <input type="file" name="img" multiple>
```
 
###pattern 屬性
pattern 屬性規定用於檢查 `<input>` 元素值的正則表達式。
pattern 屬性適用於以下輸入類型：text、search、url、tel、email、and password。

只能包含三個字母的輸入字段（無數字或特殊字符）：
```html
 Country code: 
<input type="text" name="country_code" pattern="[A-Za-z]{3}" title="Three letter country code">
```
 
###placeholder 屬性
placeholder 屬性規定用以描述輸入字段預期值的提示（樣本值或有關格式的簡短描述）。
該提示會在用戶輸入值之前顯示在輸入字段中。
placeholder 屬性適用於以下輸入類型：text、search、url、tel、email 以及 password。

擁有佔位符文本的輸入字段：
```html
 <input type="text" name="fname" placeholder="First name">
```
 
###required 屬性
required 屬性是`bool`屬性。
如果設置，則規定在提交表單之前必須填寫輸入字段。
required 屬性適用於以下輸入類型：text、search、url、tel、email、password、date pickers、number、checkbox、radio、and file.

必填的輸入字段：
```html
 Username: <input type="text" name="usrname" required>
```
 
###step 屬性
step 屬性規定 `<input>` 元素的合法數字間隔。
示例：如果 step="3"，則合法數字應該是 -3、0、3、6、等等。
提示：step 屬性可與 max 以及 min 屬性一同使用，來創建合法值的範圍。
step 屬性適用於以下輸入類型：number、range、date、datetime、datetime-local、month、time 以及 week。

擁有具體的合法數字間隔的輸入字段：
```html
 <input type="number" name="points" step="3">
 ```
 