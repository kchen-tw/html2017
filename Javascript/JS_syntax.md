##JavaScript 語句
JavaScript 語句向瀏覽器發出的命令。語句的作用是告訴瀏覽器該做什麼。
下面的 JavaScript 語句向 id="demo" 的 HTML 元素輸出文本 "Hello World"：
document.getElementById("demo").innerHTML="Hello World";
###分號 ;
分號用於分隔 JavaScript 語句。
通常我們在每條可執行的語句結尾添加分號。
使用分號的另一用處是在一行中編寫多條語句。
提示：您也可能看到不帶有分號的案例。
在 JavaScript 中，用分號來結束語句是可選的。
###JavaScript 代碼
JavaScript 代碼（或者只有 JavaScript）是 JavaScript 語句的序列。
瀏覽器會按照編寫順序來執行每條語句。
本例將操作兩個 HTML 元素：
```
document.getElementById("demo").innerHTML="Hello World";
document.getElementById("myDIV").innerHTML="How are you?";
```
###JavaScript 代碼塊
JavaScript 語句通過代碼塊的形式進行組合。
塊由左花括號開始，由右花括號結束。
塊的作用是使語句序列一起執行。
JavaScript 函數是將語句組合在塊中的典型例子。
下面的例子將運行可操作兩個 HTML 元素的函數：
```
function myFunction()
{
document.getElementById("demo").innerHTML="Hello World";
document.getElementById("myDIV").innerHTML="How are you?";
}
```

###JavaScript 對大小寫敏感。
JavaScript 對大小寫是敏感的。
當編寫 JavaScript 語句時，請留意是否關閉大小寫切換鍵。
函數 getElementById 與 getElementbyID 是不同的。
同樣，變量 myVariable 與 MyVariable 也是不同的。
###空格
JavaScript 會忽略多餘的空格。您可以向腳本添加空格，來提高其可讀性。下面的兩行代碼是等效的：
```
var name="Hello";
var name = "Hello";
```
###對代碼行進行折行
您可以在文本字符串中使用反斜槓對代碼行進行換行。下面的例子會正確地顯示：
document.write("Hello \
World!");
不過，您不能像這樣折行：
document.write \
("Hello World!");