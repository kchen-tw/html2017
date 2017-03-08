變量是存儲信息的容器。
```
var x=2;
var y=3;
var z=x+y;
```
就像代數那樣
x=2
y=3
z=x+y
在代數中，我們使用字母（比如 x）來保存值（比如 2）。
通過上面的表達式 z=x+y，我們能夠計算出 z 的值為 5。
在 JavaScript 中，這些字母被稱為變量。
提示：您可以把變量看做存儲數據的容器。
##JavaScript 變量
與代數一樣，JavaScript 變量可用於存放值（比如 x=2）和表達式（比如 z=x+y）。
變量可以使用短名稱（比如 x 和 y），也可以使用描述性更好的名稱（比如 age, sum, totalvolume）。
變量必須以字母開頭
變量也能以 $ 和 _ 符號開頭（不過我們不推薦這麼做）
變量名稱對大小寫敏感（y 和 Y 是不同的變量）
提示：JavaScript 語句和 JavaScript 變量都對大小寫敏感。
###JavaScript 數據類型
JavaScript 變量還能保存其他數據類型，比如文本值 (name="Bill Gates")。
在 JavaScript 中，類似 "Bill Gates" 這樣一條文本被稱為字符串。
JavaScript 變量有很多種類型，但是現在，我們只關注數字和字符串。
當您向變量分配文本值時，應該用雙引號或單引號包圍這個值。
當您向變量賦的值是數值時，不要使用引號。如果您用引號包圍數值，該值會被作為文本來處理。
```
var pi=3.14;
var name="Bill Gates";
var answer='Yes I am!';
```
###聲明（創建） JavaScript 變量
在 JavaScript 中創建變量通常稱為「聲明」變量。
我們使用 var 關鍵詞來聲明變量：
`var carname;`
變量聲明之後，該變量是空的（它沒有值）。
如需向變量賦值，請使用等號：
`carname="Volvo";`
不過，您也可以在聲明變量時對其賦值：
`var carname="Volvo";`

在下面的例子中，我們創建了名為 carname 的變量，並向其賦值 "Volvo"，然後把它放入 id="demo" 的 HTML 段落中：
```
<p id="demo"></p>
var carname="Volvo";
document.getElementById("demo").innerHTML=carname;
```
提示：一個好的編程習慣是，在代碼開始處，統一對需要的變量進行聲明。
###一條語句，多個變量
您可以在一條語句中聲明很多變量。該語句以 var 開頭，並使用逗號分隔變量即可：
`var name="Gates", age=56, job="CEO";`
聲明也可橫跨多行：
```
var name="Gates",
age=56,
job="CEO";
Value = undefined
```
在計算機程序中，經常會聲明無值的變量。未使用值來聲明的變量，其值實際上是 `undefined`。
在執行過以下語句後，變量 carname 的值將是 undefined：
`var carname;`
###重新聲明 JavaScript 變量
如果重新聲明 JavaScript 變量，該變量的值不會丟失：
在以下兩條語句執行後，變量 carname 的值依然是 "Volvo"：
```
var carname="Volvo";
var carname;
```
###JavaScript 算數
您可以通過 JavaScript 變量來做算數，使用的是 = 和 + 這類運算符：
```
y=5;
x=y+2;
```