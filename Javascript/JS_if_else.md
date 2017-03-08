條件語句用於基於不同的條件來執行不同的動作。
##條件語句
通常在寫代碼時，您總是需要為不同的決定來執行不同的動作。您可以在代碼中使用條件語句來完成該任務。
在 JavaScript 中，我們可使用以下條件語句：
if 語句 - 只有當指定條件為 true 時，使用該語句來執行代碼
if...else 語句 - 當條件為 true 時執行代碼，當條件為 false 時執行其他代碼
if...else if....else 語句 - 使用該語句來選擇多個代碼塊之一來執行
switch 語句 - 使用該語句來選擇多個代碼塊之一來執行
###If 語句
只有當指定條件為 true 時，該語句才會執行代碼。
語法
```
if (條件)
  {
  只有當條件為 true 時執行的代碼
  }
```
注意：請使用小寫的 if。使用大寫字母（IF）會生成 JavaScript 錯誤！

當時間小於 20:00 時，生成一個「Good day」問候：
```
if (time<20)
  {
  x="Good day";
  }
```
x 的結果是：
`Good day`

請注意，在這個語法中，沒有 ..else..。您已經告訴瀏覽器只有在指定條件為 true 時才執行代碼。
###If...else 語句
請使用 if....else 語句在條件為 true 時執行代碼，在條件為 false 時執行其他代碼。
語法
```
if (條件)
  {
  當條件為 true 時執行的代碼
  }
else
  {
  當條件不為 true 時執行的代碼
  }
```
當時間小於 20:00 時，將得到問候 "Good day"，否則將得到問候 "Good evening"。
```
if (time<20)
  {
  x="Good day";
  }
else
  {
  x="Good evening";
  }
```
x 的結果是：
`Good day`

###If...else if...else 語句
使用 if....else if...else 語句來選擇多個代碼塊之一來執行。
語法
```
if (條件 1)
  {
  當條件 1 為 true 時執行的代碼
  }
else if (條件 2)
  {
  當條件 2 為 true 時執行的代碼
  }
else
  {
  當條件 1 和 條件 2 都不為 true 時執行的代碼
  }
```

如果時間小於 10:00，則將發送問候 "Good morning"，否則如果時間小於 20:00，則發送問候 "Good day"，否則發送問候 "Good evening"：
```
if (time<10)
  {
  x="Good morning";
  }
else if (time<20)
  {
  x="Good day";
  }
else
  {
  x="Good evening";
  }
```
x 的結果是：
`Good day`

###switch 語句用於基於不同的條件來執行不同的動作。
JavaScript Switch 語句
請使用 switch 語句來選擇要執行的多個代碼塊之一。
語法
```
switch(n)
{
case 1:
  執行代碼塊 1
  break;
case 2:
  執行代碼塊 2
  break;
default:
  n 與 case 1 和 case 2 不同時執行的代碼
}
```
工作原理：首先設置表達式 n（通常是一個變量）。隨後表達式的值會與結構中的每個 case 的值做比較。如果存在匹配，則與該 case 關聯的代碼塊會被執行。請使用 break 來阻止代碼自動地向下一個 case 運行。

顯示今日的周名稱。請注意 Sunday=0, Monday=1, Tuesday=2, 等等：
```
var day=new Date().getDay();
switch (day)
{
case 0:
  x="Today it's Sunday";
  break;
case 1:
  x="Today it's Monday";
  break;
case 2:
  x="Today it's Tuesday";
  break;
case 3:
  x="Today it's Wednesday";
  break;
case 4:
  x="Today it's Thursday";
  break;
case 5:
  x="Today it's Friday";
  break;
case 6:
  x="Today it's Saturday";
  break;
}
```
x 的結果：
`Today it's Wednesday`

####default 關鍵詞
請使用 default 關鍵詞來規定匹配不存在時做的事情：

如果今天不是週六或周日，則會輸出默認的消息：
```
var day=new Date().getDay();
switch (day)
{
case 6:
  x="Today it's Saturday";
  break;
case 0:
  x="Today it's Sunday";
  break;
default:
  x="Looking forward to the Weekend";
}
```
x 的結果：
`Looking forward to the Weekend`
