JavaScript 可用來在數據被送往服務器前對 HTML 表單中的這些輸入數據進行驗證。
##JavaScript 表單驗證
JavaScript 可用來在數據被送往服務器前對 HTML 表單中的這些輸入數據進行驗證。
被 JavaScript 驗證的這些典型的表單數據有：
* 用戶是否已填寫表單中的必填項目？
* 用戶輸入的郵件地址是否合法？
* 用戶是否已輸入合法的日期？
* 用戶是否在數據域 (numeric field) 中輸入了文本？

###必填（或必選）項目
下面的函數用來檢查用戶是否已填寫表單中的必填（或必選）項目。假如必填或必選項為空，那麼警告框會彈出，並且函數的返回值為 false，否則函數的返回值則為 true（意味著數據沒有問題）：
```
function validate_required(field,alerttxt)
{
with (field)
{
if (value==null||value=="")
  {alert(alerttxt);return false}
else {return true}
}
}
```
下面是連同 HTML 表單的代碼：
```html
<html>
<head>
<script type="text/javascript">

function validate_required(field,alerttxt)
{
with (field)
  {
  if (value==null||value=="")
    {alert(alerttxt);return false}
  else {return true}
  }
}

function validate_form(thisform)
{
with (thisform)
  {
  if (validate_required(email,"Email must be filled out!")==false)
    {email.focus();return false}
  }
}
</script>
</head>

<body>
<form action="submitpage.htm" onsubmit="return validate_form(this)" method="post">
Email: <input type="text" name="email" size="30">
<input type="submit" value="Submit"> 
</form>
</body>

</html>
```
####E-mail 驗證
下面的函數檢查輸入的數據是否符合電子郵件地址的基本語法。
意思就是說，輸入的數據必須包含 @ 符號和點號(.)。同時，@ 不可以是郵件地址的首字符，並且 @ 之後需有至少一個點號：
```
function validate_email(field,alerttxt)
{
with (field)
{
apos=value.indexOf("@")
dotpos=value.lastIndexOf(".")
if (apos<1||dotpos-apos<2) 
  {alert(alerttxt);return false}
else {return true}
}
}
```
下面是連同 HTML 表單的完整代碼：
```html
<html>
<head>
<script type="text/javascript">
function validate_email(field,alerttxt)
{
with (field)
{
apos=value.indexOf("@")
dotpos=value.lastIndexOf(".")
if (apos<1||dotpos-apos<2) 
  {alert(alerttxt);return false}
else {return true}
}
}

function validate_form(thisform)
{
with (thisform)
{
if (validate_email(email,"Not a valid e-mail address!")==false)
  {email.focus();return false}
}
}
</script>
</head>

<body>
<form action="submitpage.htm"onsubmit="return validate_form(this);" method="post">
Email: <input type="text" name="email" size="30">
<input type="submit" value="Submit"> 
</form>
</body>

</html>
```