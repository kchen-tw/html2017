### `<input>` 元素
`<input>` 元素是最重要的表單元素。
`<input>` 元素有很多形態，根據不同的 type 屬性。
這是本章中使用的類型：
text：	定義常規文本輸入。
radio：	定義單選按鈕輸入（選擇多個選擇之一）
submit：	定義提交按鈕（提交表單）

#### 文本输入
`<input type="text">` 定義用於文本輸入的單行輸入字段：
```html
<form>
First name:<br>
<input type="text" name="firstname">
<br>
Last name:<br>
<input type="text" name="lastname">
</form>
```
<form> First name:<br> <input type="text" name="firstname"> <br> Last name:<br> <input type="text" name="lastname"> </form>

#### 輸入類型：password
`<input type="password">` 定義密碼字段：
```html
<form>
 User name:<br>
<input type="text" name="username">
<br>
 User password:<br>
<input type="password" name="psw">
</form> 
```
<form>
User name:<br>
<input type="text" name="username">
<br>
User password:<br>
<input type="password" name="psw">
</form>

#### 單選按鈕輸入
`<input type="radio">` 定義單選按鈕。
單選按鈕允許用戶在有限數量的選項中選擇其中之一：
```html
<form>
<input type="radio" name="sex" value="male" checked>Male
<input type="radio" name="sex" value="female">Female
</form>
```
<form> <input type="radio" name="sex" value="male" checked>Male <input type="radio" name="sex" value="female">Female </form>
#### 提交按鈕
`<input type="submit">` 定義用於向表單處理程序（form-handler）提交表單的按鈕。
表單處理程序通常是包含用來處理輸入數據的腳本的服務器頁面。
表單處理程序在表單的 action 屬性中指定：
```html
<form action="action_page.php">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form>
```
<form action="action_page.php"> First name:<br> <input type="text" name="firstname" value="Mickey"> <br> Last name:<br> <input type="text" name="lastname" value="Mouse"> <br><br> <input type="submit" value="Submit"> </form>

#### `<select>` 元素（下拉列表）
`<select>` 元素定義下拉列表：
```html
<select name="cars">
<option value="volvo">Volvo</option>
<option value="saab">Saab</option>
<option value="fiat">Fiat</option>
<option value="audi">Audi</option>
</select>
```

#### Input Type: checkbox
`<input type="checkbox">` 定義復選框。
Checkboxes let a user select ZERO or MORE options of a limited number of choices.
```html
<form>
<input type="checkbox" name="vehicle" value="Bike">I have a bike
<br>
<input type="checkbox" name="vehicle" value="Car">I have a car 
</form> 
```
<form> <input type="checkbox" name="vehicle" value="Bike">I have a bike <br> <input type="checkbox" name="vehicle" value="Car">I have a car </form>

#### Input Type: button
`<input type="button>` 定義按鈕。
```html
<input type="button" onclick="alert('Hello World!')" value="Click Me!">
```
<input type="button" onclick="alert('Hello World!')" value="Click Me!">

#### `<option>` 元素定義待選擇的選項。
列表通常會把首個選項顯示為被選選項。
您能夠通過添加 selected 屬性來定義預定義選項。
```html
<option value="fiat" selected>Fiat</option>
```

#### `<textarea>` 元素
`<textarea>` 元素定義多行輸入字段（文本域）：
```html
<textarea name="message" rows="10" cols="30">
The cat was playing in the garden.
</textarea>
```

### HTML5 輸入類型
HTML5 增加了多個新的輸入類型：
color
date
datetime
datetime-local
email
month
number
range
search
tel
time
url
week

#### 輸入類型：number
`<input type="number">` 用於應該包含數字值的輸入字段。
您能夠對數字做出限制。
根據瀏覽器支持，限制可應用到輸入字段。
```html
<form>
  Quantity (between 1 and 5):
  <input type="number" name="quantity" min="1" max="5">
</form>
```
<form> Quantity (between 1 and 5): <input type="number" name="quantity" min="1" max="5"> </form>

#### 輸入類型：date
`<input type="date">` 用於應該包含日期的輸入字段。
根據瀏覽器支持，日期選擇器會出現輸入字段中。
```html
<form>
  Birthday:
  <input type="date" name="bday">
</form>
```
  <form> Birthday: <input type="date" name="bday"> </form>

#### 輸入類型：color
`<input type="color">` 用於應該包含顏色的輸入字段。
根據瀏覽器支持，顏色選擇器會出現輸入字段中。
```html
<form>
  Select your favorite color:
  <input type="color" name="favcolor">
</form>
```
<form> Select your favorite color: <input type="color" name="favcolor"> </form>

####輸入類型：range
`<input type="range">` 用於應該包含一定範圍內的值的輸入字段。
根據瀏覽器支持，輸入字段能夠顯示為滑塊控件。
```html
<form>
  <input type="range" name="points" min="0" max="10">
</form>
```
<form> <input type="range" name="points" min="0" max="10"> </form>

#### 輸入類型：month
`<input type="month">` 允許用戶選擇月份和年份。
根據瀏覽器支持，日期選擇器會出現輸入字段中。
```html
<form>
  Birthday (month and year):
  <input type="month" name="bdaymonth">
</form>
```
 <form> Birthday (month and year): <input type="month" name="bdaymonth"> </form>
   
#### 輸入類型：week
`<input type="week">` 允許用戶選擇周和年。
根據瀏覽器支持，日期選擇器會出現輸入字段中。
```html
<form>
  Select a week:
  <input type="week" name="week_year">
</form>
```
<form> Select a week: <input type="week" name="week_year"> </form>
  
#### 輸入類型：time
`<input type="time">` 允許用戶選擇時間（無時區）。
根據瀏覽器支持，時間選擇器會出現輸入字段中。
```html
<form>
  Select a time:
  <input type="time" name="usr_time">
</form>
```
<form> Select a time: <input type="time" name="usr_time"> </form>
  
####輸入類型：datetime
`<input type="datetime">` 允許用戶選擇日期和時間（有時區）。
根據瀏覽器支持，日期選擇器會出現輸入字段中。
```html
<form>
  Birthday (date and time):
  <input type="datetime" name="bdaytime">
</form>
```
  <form> Birthday (date and time): <input type="datetime" name="bdaytime"> </form>
  
#### 輸入類型：email
`<input type="email">` 用於應該包含電子郵件地址的輸入字段。
根據瀏覽器支持，能夠在被提交時自動對電子郵件地址進行驗證。
某些智能手機會識別 email 類型，並在鍵盤增加 ".com" 以匹配電子郵件輸入。
```html
<form>
  E-mail:
  <input type="email" name="email">
</form>
```
  <form> E-mail: <input type="email" name="email"> </form>

#### 輸入類型：tel
`<input type="tel">` 用於應該包含電話號碼的輸入字段。
目前只有 Safari 8 支持 tel 類型。
```html
<form>
  Telephone:
  <input type="tel" name="usrtel">
</form>
```
  <form> Telephone: <input type="tel" name="usrtel"> </form>

  #### 輸入類型：url
`<input type="url">` 用於應該包含 URL 地址的輸入字段。
根據瀏覽器支持，在提交時能夠自動驗證 url 字段。
某些智能手機識別 url 類型，並向鍵盤添加 ".com" 以匹配 url 輸入。
```html
<form>
  Add your homepage:
  <input type="url" name="homepage">
</form>
  ```
<form> Add your homepage: <input type="url" name="homepage"> </form>
