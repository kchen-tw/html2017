循環可以將代碼塊執行指定的次數。
##JavaScript 循環
如果您希望一遍又一遍地運行相同的代碼，並且每次的值都不同，那麼使用循環是很方便的。
我們可以這樣輸出數組的值：
```
document.write(cars[0] + "<br>");
document.write(cars[1] + "<br>");
document.write(cars[2] + "<br>");
document.write(cars[3] + "<br>");
document.write(cars[4] + "<br>");
document.write(cars[5] + "<br>");
```
不過通常我們這樣寫：
```
for (var i=0;i<cars.length;i++)
{
document.write(cars[i] + "<br>");
}
```
###不同類型的循環
JavaScript 支持不同類型的循環：
for - 循環代碼塊一定的次數
for/in - 循環遍歷對象的屬性
while - 當指定的條件為 true 時循環指定的代碼塊
do/while - 同樣當指定的條件為 true 時循環指定的代碼塊
###For 循環
for 循環是您在希望創建循環時常會用到的工具。
下面是 for 循環的語法：
```
for (語句 1; 語句 2; 語句 3)
  {
  被執行的代碼塊
  }
```
語句 1 在循環（代碼塊）開始前執行
語句 2 定義運行循環（代碼塊）的條件
語句 3 在循環（代碼塊）已被執行之後執行
```
for (var i=0; i<5; i++)
  {
  x=x + "The number is " + i + "<br>";
  }
```
從上面的例子中，您可以看到：
Statement 1 在循環開始之前設置變量 (var i=0)。
Statement 2 定義循環運行的條件（i 必須小於 5）。
Statement 3 在每次代碼塊已被執行後增加一個值 (i++)。
語句 1
通常我們會使用語句 1 初始化循環中所用的變量 (var i=0)。
語句 1 是可選的，也就是說不使用語句 1 也可以。
您可以在語句 1 中初始化任意（或者多個）值：
```
for (var i=0,len=cars.length; i<len; i++)
{
document.write(cars[i] + "<br>");
}
```
同時您還可以省略語句 1（比如在循環開始前已經設置了值時）：
```
var i=2,len=cars.length;
for (; i<len; i++)
{
document.write(cars[i] + "<br>");
}
```
語句 2
通常語句 2 用於評估初始變量的條件。
語句 2 同樣是可選的。
如果語句 2 返回 true，則循環再次開始，如果返回 false，則循環將結束。
提示：如果您省略了語句 2，那麼必須在循環內提供 break。否則循環就無法停下來。這樣有可能令瀏覽器崩潰。請在本教程稍後的章節閱讀有關 break 的內容。
語句 3
通常語句 3 會增加初始變量的值。
語句 3 也是可選的。
語句 3 有多種用法。增量可以是負數 (i--)，或者更大 (i=i+15)。
語句 3 也可以省略（比如當循環內部有相應的代碼時）：
```
var i=0,len=cars.length;
for (; i<len; )
{
document.write(cars[i] + "<br>");
i++;
}
```
###For/In 循環
JavaScript for/in 語句循環遍歷對象的屬性：
```
var person={fname:"John",lname:"Doe",age:25};

for (x in person)
  {
  txt=txt + person[x];
  }
```
您將在有關 JavaScript 對象的章節學到更多有關 for / in 循環的知識。

###While 循環

只要指定條件為 true，循環就可以一直執行代碼。
While 循環會在指定條件為真時循環執行代碼塊。
語法
```
while (條件)
  {
  需要執行的代碼
  }
```
本例中的循環將繼續運行，只要變量 i 小於 5：
```
while (i<5)
  {
  x=x + "The number is " + i + "<br>";
  i++;
  }
```
提示：如果您忘記增加條件中所用變量的值，該循環永遠不會結束。該可能導致瀏覽器崩潰。
###do/while 循環
do/while 循環是 while 循環的變體。該循環會執行一次代碼塊，在檢查條件是否為真之前，然後如果條件為真的話，就會重復這個循環。
語法
```
do
  {
  需要執行的代碼
  }
while (條件);
```
下面的例子使用 do/while 循環。該循環至少會執行一次，即使條件是 false，隱藏代碼塊會在條件被測試前執行：
```
do
  {
  x=x + "The number is " + i + "<br>";
  i++;
  }
while (i<5);
```
別忘記增加條件中所用變量的值，否則循環永遠不會結束！
###比較 for 和 while
如果您已經閱讀了前面那一章關於 for 循環的內容，您會發現 while 循環與 for 循環很像。
for 語句實例
本例中的循環使用 for 循環來顯示 cars 數組中的所有值：
```
cars=["BMW","Volvo","Saab","Ford"];
var i=0;
for (;cars[i];)
{
document.write(cars[i] + "<br>");
i++;
}
```
while 語句實例
本例中的循環使用使用 while 循環來顯示 cars 數組中的所有值：
```
cars=["BMW","Volvo","Saab","Ford"];
var i=0;
while (cars[i])
{
document.write(cars[i] + "<br>");
i++;
}
```

break 語句用於跳出循環。
continue 用於跳過循環中的一個迭代。
###Break 語句
我們已經在本教程稍早的章節中見到過 break 語句。它用於跳出 switch() 語句。
####break 語句可用於跳出循環。
break 語句跳出循環後，會繼續執行該循環之後的代碼（如果有的話）：
```
for (i=0;i<10;i++)
  {
  if (i==3)
    {
    break;
    }
  x=x + "The number is " + i + "<br>";
  }
```
由於這個 if 語句只有一行代碼，所以可以省略花括號：
```
for (i=0;i<10;i++)
  {
  if (i==3) break;
  x=x + "The number is " + i + "<br>";
  }
```
###Continue 語句
continue 語句中斷循環中的迭代，如果出現了指定的條件，然後繼續循環中的下一個迭代。
該例子跳過了值 3：
```
for (i=0;i<=10;i++)
 {
 if (i==3) continue;
  x=x + "The number is " + i + "<br>";
  }
```
###JavaScript 標籤
正如您在 switch 語句那一章中看到的，可以對 JavaScript 語句進行標記。
如需標記 JavaScript 語句，請在語句之前加上冒號：
```
label:
語句
```
break 和 continue 語句僅僅是能夠跳出代碼塊的語句。
語法
```
break labelname;

continue labelname;
```
continue 語句（帶有或不帶標籤引用）只能用在循環中。
break 語句（不帶標籤引用），只能用在循環或 switch 中。
通過標籤引用，break 語句可用於跳出任何 JavaScript 代碼塊：
```
cars=["BMW","Volvo","Saab","Ford"];
list:
{
document.write(cars[0] + "<br>");
document.write(cars[1] + "<br>");
document.write(cars[2] + "<br>");
break list;
document.write(cars[3] + "<br>");
document.write(cars[4] + "<br>");
document.write(cars[5] + "<br>");
}
```