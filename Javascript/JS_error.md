try 語句測試代碼塊的錯誤。
catch 語句處理錯誤。
throw 語句創建自定義錯誤。
###錯誤一定會發生
當 JavaScript 引擎執行 JavaScript 代碼時，會發生各種錯誤：
可能是語法錯誤，通常是程序員造成的編碼錯誤或錯別字。
可能是拼寫錯誤或語言中缺少的功能（可能由於瀏覽器差異）。
可能是由於來自服務器或用戶的錯誤輸出而導致的錯誤。
當然，也可能是由於許多其他不可預知的因素。
###JavaScript 拋出錯誤
當錯誤發生時，當事情出問題時，JavaScript 引擎通常會停止，並生成一個錯誤消息。
描述這種情況的技術術語是：JavaScript 將拋出一個錯誤。
###JavaScript 測試和捕捉
try 語句允許我們定義在執行時進行錯誤測試的代碼塊。
catch 語句允許我們定義當 try 代碼塊發生錯誤時，所執行的代碼塊。
JavaScript 語句 try 和 catch 是成對出現的。
語法
```
try
  {
  //在這裡運行代碼
  }
catch(err)
  {
  //在這裡處理錯誤
  }
```
在下面的例子中，我們故意在 try 塊的代碼中寫了一個錯字。
catch 塊會捕捉到 try 塊中的錯誤，並執行代碼來處理它。
```html
<!DOCTYPE html>
<html>
<head>
<script>
var txt="";
function message()
{
try
  {
  adddlert("Welcome guest!");
  }
catch(err)
  {
  txt="There was an error on this page.\n\n";
  txt+="Error description: " + err.message + "\n\n";
  txt+="Click OK to continue.\n\n";
  alert(txt);
  }
}
</script>
</head>

<body>
<input type="button" value="View message" onclick="message()">
</body>

</html>
```
###Throw 語句
throw 語句允許我們創建自定義錯誤。
正確的技術術語是：創建或拋出異常（exception）。
如果把 throw 與 try 和 catch 一起使用，那麼您能夠控制程序流，並生成自定義的錯誤消息。
語法
`throw exception`
異常可以是 JavaScript 字符串、數字、邏輯值或對象。

本例檢測輸入變量的值。如果值是錯誤的，會拋出一個異常（錯誤）。catch 會捕捉到這個錯誤，並顯示一段自定義的錯誤消息：
```html
<script>
function myFunction()
{
try
  {
  var x=document.getElementById("demo").value;
  if(x=="")    throw "empty";
  if(isNaN(x)) throw "not a number";
  if(x>10)     throw "too high";
  if(x<5)      throw "too low";
  }
catch(err)
  {
  var y=document.getElementById("mess");
  y.innerHTML="Error: " + err + ".";
  }
}
</script>

<h1>My First JavaScript</h1>
<p>Please input a number between 5 and 10:</p>
<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>
<p id="mess"></p>
```
請注意，如果 getElementById 函數出錯，上面的例子也會拋出一個錯誤。