#### Action 屬性
action 屬性定義在提交表單時執行的動作。
向服務器提交表單的通常做法是使用提交按鈕。
通常，表單會被提交到 web 服務器上的網頁。
在上面的例子中，指定了某個服務器腳本來處理被提交表單：
``<form action="action_page.php">`
如果省略 action 屬性，則 action 會被設置為當前頁面。

#### Method 屬性
method 屬性規定在提交表單時所用的 HTTP 方法（GET 或 POST）：
`<form action="action_page.php" method="GET">`
或：
``<form action="action_page.php" method="POST">`

##### 何時使用 GET？
您能夠使用 GET（默認方法）：
如果表單提交是被動的（比如搜索引擎查詢），並且沒有敏感信息。
當您使用 GET 時，表單數據在頁面地址欄中是可見的：
`action_page.php?firstname=Mickey&lastname=Mouse`

##### 何時使用 POST？
您應該使用 POST：
如果表單正在更新數據，或者包含敏感信息（例如密碼）。
POST 的安全性更加，因為在頁面地址欄中被提交的數據是不可見的。

#### Name 屬性
如果要正確地被提交，每個輸入字段必須設置一個 name 屬性。
本例只會提交 "Last name" 輸入字段：
```html
<form action="action_page.php">
First name:<br>
<input type="text" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
```
 
###HTML Form 屬性
HTML `<form>` 元素，已設置所有可能的屬性，是這樣的：
```html
<form action="action_page.php" method="GET" target="_blank" accept-charset="UTF-8" ectype="application/x-www-form-urlencoded" autocomplete="off" novalidate>
form elements
</form>
 ```