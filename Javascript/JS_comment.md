JavaScript 注釋可用於提高代碼的可讀性。
##JavaScript 注釋
JavaScript 不會執行注釋。
我們可以添加註釋來對 JavaScript 進行解釋，或者提高代碼的可讀性。
單行注釋以 `//` 開頭。
例子
下面的例子使用單行注釋來解釋代碼：
```
// 輸出標題：
document.getElementById("myH1").innerHTML="Welcome to my Homepage";
// 輸出段落：
document.getElementById("myP").innerHTML="This is my first paragraph.";
```
###JavaScript 多行注釋
多行注釋以 `/*` 開始，以 `*/` 結尾。
下面的例子使用多行注釋來解釋代碼：
例子
```
/*
下面的這些代碼會輸出
一個標題和一個段落
並將代表主頁的開始
*/
document.getElementById("myH1").innerHTML="Welcome to my Homepage";
document.getElementById("myP").innerHTML="This is my first paragraph.";
```
使用注釋來阻止執行
例子 1
在下面的例子中，注釋用於阻止其中一條代碼行的執行（可用於調試）：
```
//document.getElementById("myH1").innerHTML="Welcome to my Homepage";
document.getElementById("myP").innerHTML="This is my first paragraph.";
```
例子 2
在下面的例子中，注釋用於阻止代碼塊的執行（可用於調試）：
```
/*
document.getElementById("myH1").innerHTML="Welcome to my Homepage";
document.getElementById("myP").innerHTML="This is my first paragraph.";
*/
```
在行末使用注釋
在下面的例子中，我們把注釋放到代碼行的結尾處：
例子
```
var x=5;    // 聲明 x 並把 5 賦值給它
var y=x+2;  // 聲明 y 並把 x+2 賦值給它
```