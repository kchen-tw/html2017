函數是由事件驅動的或者當它被調用時執行的可重復使用的代碼塊。
```
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction()
{
alert("Hello World!");
}
</script>
</head>

<body>
<button onclick="myFunction()">點擊這裡</button>
</body>
</html>
```
###JavaScript 函數語法
函數就是包裹在花括號中的代碼塊，前面使用了關鍵詞 function：
```
function functionname()
{
這裡是要執行的代碼
}
```
當調用該函數時，會執行函數內的代碼。
可以在某事件發生時直接調用函數（比如當用戶點擊按鈕時），並且可由 JavaScript 在任何位置進行調用。
提示：JavaScript 對大小寫敏感。關鍵詞 function 必須是小寫的，並且必須以與函數名稱相同的大小寫來調用函數。
###調用帶參數的函數
在調用函數時，您可以向其傳遞值，這些值被稱為參數。
這些參數可以在函數中使用。
您可以發送任意多的參數，由逗號 (,) 分隔：
`myFunction(argument1,argument2)`
當您聲明函數時，請把參數作為變量來聲明：
```
function myFunction(var1,var2)
{
這裡是要執行的代碼
}
```
變量和參數必須以一致的順序出現。第一個變量就是第一個被傳遞的參數的給定的值，以此類推。
```
<button onclick="myFunction('Bill Gates','CEO')">點擊這裡</button>

<script>
function myFunction(name,job)
{
alert("Welcome " + name + ", the " + job);
}
</script>
```
上面的函數會當按鈕被點擊時提示 "Welcome Bill Gates, the CEO"。
函數很靈活，您可以使用不同的參數來調用該函數，這樣就會給出不同的消息：
```
<button onclick="myFunction('Harry Potter','Wizard')">點擊這裡</button>
<button onclick="myFunction('Bob','Builder')">點擊這裡</button>
```
根據您點擊的不同的按鈕，上面的例子會提示 "Welcome Harry Potter, the Wizard" 或 "Welcome Bob, the Builder"。
###帶有返回值的函數
有時，我們會希望函數將值返回調用它的地方。
通過使用 return 語句就可以實現。
在使用 return 語句時，函數會停止執行，並返回指定的值。
```
function myFunction()
{
var x=5;
return x;
}
```
上面的函數會返回值 5。
注釋：整個 JavaScript 並不會停止執行，僅僅是函數。JavaScript 將繼續執行代碼，從調用函數的地方。
###函數調用將被返回值取代：
`var myVar=myFunction();`
myVar 變量的值是 5，也就是函數 "myFunction()" 所返回的值。
即使不把它保存為變量，您也可以使用返回值：
`document.getElementById("demo").innerHTML=myFunction();`
"demo" 元素的 innerHTML 將成為 5，也就是函數 "myFunction()" 所返回的值。
您可以使返回值基於傳遞到函數中的參數：

計算兩個數字的乘積，並返回結果：
```
function myFunction(a,b)
{
return a*b;
}

document.getElementById("demo").innerHTML=myFunction(4,3);
```
"demo" 元素的 innerHTML 將是：
`12`

在您僅僅希望退出函數時 ，也可使用 return 語句。返回值是可選的：
```
function myFunction(a,b)
{
if (a>b)
  {
  return;
  }
x=a+b
}
```
如果 a 大於 b，則上面的代碼將退出函數，並不會計算 a 和 b 的總和。
###局部 JavaScript 變量
在 JavaScript 函數內部聲明的變量（使用 var）是局部變量，所以只能在函數內部訪問它。（該變量的作用域是局部的）。
您可以在不同的函數中使用名稱相同的局部變量，因為只有聲明過該變量的函數才能識別出該變量。
只要函數運行完畢，本地變量就會被刪除。
###全局 JavaScript 變量
在函數外聲明的變量是全局變量，網頁上的所有腳本和函數都能訪問它。
###JavaScript 變量的生存期
JavaScript 變量的生命期從它們被聲明的時間開始。
局部變量會在函數運行以後被刪除。
全局變量會在頁面關閉後被刪除。
###向未聲明的 JavaScript 變量來分配值
如果您把值賦給尚未聲明的變量，該變量將被自動作為全局變量聲明。
這條語句：
`carname="Volvo";`
將聲明一個全局變量 carname，即使它在函數內執行。