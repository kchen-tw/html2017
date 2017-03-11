JavaScript 中的所有事物都是對象：字符串、數值、數組、函數...
此外，JavaScript 允許自定義對象。
##JavaScript 對象
JavaScript 提供多個內建對象，比如 String、Date、Array 等等。
對象只是帶有屬性和方法的特殊數據類型。
###訪問對象的屬性
屬性是與對象相關的值。
訪問對象屬性的語法是：
`objectName.propertyName`
這個例子使用了 String 對象的 length 屬性來獲得字符串的長度：
```
var message="Hello World!";
var x=message.length;
```
在以上代碼執行後，x 的值將是：
`12`
###訪問對象的方法
方法是能夠在對象上執行的動作。
您可以通過以下語法來調用方法：
`objectName.methodName()`
這個例子使用了 String 對象的 toUpperCase() 方法來將文本轉換為大寫：
```
var message="Hello world!";
var x=message.toUpperCase();
```
在以上代碼執行後，x 的值將是：
`HELLO WORLD!`
###創建 JavaScript 對象
通過 JavaScript，您能夠定義並創建自己的對象。
創建新對象有兩種不同的方法：
定義並創建對象的實例
使用函數來定義對象，然後創建新的對象實例
創建直接的實例
這個例子創建了對象的一個新實例，並向其添加了四個屬性：
```
person=new Object();
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";
```
替代語法（使用對象 literals）：
`person={firstname:"John",lastname:"Doe",age:50,eyecolor:"blue"};`

###使用對象構造器
本例使用函數來構造對象：
```
function person(firstname,lastname,age,eyecolor)
{
this.firstname=firstname;
this.lastname=lastname;
this.age=age;
this.eyecolor=eyecolor;
}
```
###創建 JavaScript 對象實例
一旦您有了對象構造器，就可以創建新的對象實例，就像這樣：
```
var myFather=new person("Bill","Gates",56,"blue");
var myMother=new person("Steve","Jobs",48,"green");
```
###把屬性添加到 JavaScript 對象
您可以通過為對象賦值，向已有對象添加新屬性：
假設 personObj 已存在 - 您可以為其添加這些新屬性：firstname、lastname、age 以及 eyecolor：
```
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";

x=person.firstname;
```
在以上代碼執行後，x 的值將是：
`Bill`
###把方法添加到 JavaScript 對象
方法只不過是附加在對象上的函數。
在構造器函數內部定義對象的方法：
```
function person(firstname,lastname,age,eyecolor)
{
  this.firstname=firstname;
  this.lastname=lastname;
  this.age=age;
  this.eyecolor=eyecolor;

  this.changeName=changeName;
  function changeName(name){
    this.lastname=name;
  }
}
```
changeName() 函數 name 的值賦給 person 的 lastname 屬性。
現在您可以試一下：
`myMother.changeName("Ballmer");`

###JavaScript 類
JavaScript 是面向對象的語言，但 JavaScript 不使用類。
在 JavaScript 中，不會創建類，也不會通過類來創建對象（就像在其他面向對象的語言中那樣）。
JavaScript 基於 prototype，而不是基於類的。
###JavaScript for...in 循環
JavaScript for...in 語句循環遍歷對象的屬性。
語法
```
for (對象中的變量)
  {
  要執行的代碼
  }
```
注釋：for...in 循環中的代碼塊將針對每個屬性執行一次。

循環遍歷對象的屬性：
```
var person={fname:"Bill",lname:"Gates",age:56};

for (x in person)
  {
  txt=txt + person[x];
  }
```

JavaScript 只有一種數字類型。
可以使用也可以不使用小數點來書寫數字。
###JavaScript 數字
JavaScript 數字可以使用也可以不使用小數點來書寫：
```
var pi=3.14;    // 使用小數點
var x=34;       // 不使用小數點
```
極大或極小的數字可通過科學（指數）計數法來寫：
```
var y=123e5;    // 12300000
var z=123e-5;   // 0.00123
```
####所有 JavaScript 數字均為 64 位
JavaScript 不是類型語言。與許多其他編程語言不同，JavaScript 不定義不同類型的數字，比如整數、短、長、浮點等等。
JavaScript 中的所有數字都存儲為根為 10 的 64 位浮點數。
####精度
整數（不使用小數點或指數計數法）最多為 15 位。
小數的最大位數是 17，但是浮點運算並不總是 100% 準確：
`var x=0.2+0.1;`

####八進制和十六進制
如果前綴為 0，則 JavaScript 會把數值常量解釋為八進制數，如果前綴為 0 和 "x"，則解釋為十六進制數。
```
var y=0377;
var z=0xFF;
```
提示：絕不要在數字前面寫零，除非您需要進行八進制轉換。
####數字屬性和方法
屬性：
* MAX VALUE
* MIN VALUE
* NEGATIVE INFINITIVE
* POSITIVE INFINITIVE
* NaN
* prototype
* constructor
方法：
* toExponential()
* toFixed()
* toPrecision()
* toString()
* valueOf()

String 對象用於處理已有的字符塊。
###JavaScript String（字符串）
* 計算字符串的長度
如何使用長度屬性來計算字符串的長度。
```
var txt="Hello World!"
document.write(txt.length)
```
* 為字符串添加樣式
如何為字符串添加樣式。

```html
<html>
<body>

<script type="text/javascript">

var txt="Hello World!"

document.write("<p>Big: " + txt.big() + "</p>")
document.write("<p>Small: " + txt.small() + "</p>")

document.write("<p>Bold: " + txt.bold() + "</p>")
document.write("<p>Italic: " + txt.italics() + "</p>")

document.write("<p>Blink: " + txt.blink() + " (does not work in IE)</p>")
document.write("<p>Fixed: " + txt.fixed() + "</p>")
document.write("<p>Strike: " + txt.strike() + "</p>")

document.write("<p>Fontcolor: " + txt.fontcolor("Red") + "</p>")
document.write("<p>Fontsize: " + txt.fontsize(16) + "</p>")

document.write("<p>Lowercase: " + txt.toLowerCase() + "</p>")
document.write("<p>Uppercase: " + txt.toUpperCase() + "</p>")

document.write("<p>Subscript: " + txt.sub() + "</p>")
document.write("<p>Superscript: " + txt.sup() + "</p>")

document.write("<p>Link: " + txt.link("http://www.w3school.com.cn") + "</p>")
</script>

</body>
</html>
```
* indexOf() 方法
如何使用 indexOf() 來定位字符串中某一個指定的字符首次出現的位置。
```
var str="Hello world!"
str.indexOf("Hello");  //0
str.indexOf("World");  //-1
str.indexOf("world");  //6
```
* match() 方法
如何使用 match() 來查找字符串中特定的字符，並且如果找到的話，則返回這個字符。
```
var str="Hello world!"
str.match("world"); //world
str.match("World"); //null
str.match("worlld"); //null
str.match("world!"); //world!
```
* 如何替換字符串中的字符 - replace()
如何使用 replace() 方法在字符串中用某些字符替換另一些字符。
```
var str="Visit Microsoft!"
str.replace(/Microsoft/,"W3School");  //"Visit W3School"
```

日期對象用於處理日期和時間。
###JavaScript Date（日期）
####定義日期
Date 對象用於處理日期和時間。
可以通過 new 關鍵詞來定義 Date 對象。以下代碼定義了名為 myDate 的 Date 對象：
`var myDate=new Date()` 
注釋：Date 對象自動使用當前的日期和時間作為其初始值。
####操作日期
通過使用針對日期對象的方法，我們可以很容易地對日期進行操作。
在下面的例子中，我們為日期對象設置了一個特定的日期 (2008 年 8 月 9 日)：
```
var myDate=new Date()
myDate.setFullYear(2008,7,9)
```
注意：表示月份的參數介於 0 到 11 之間。也就是說，如果希望把月設置為 8 月，則參數應該是 7。
在下面的例子中，我們將日期對象設置為 5 天後的日期：
```
var myDate=new Date()
myDate.setDate(myDate.getDate()+5)
```
注意：如果增加天數會改變月份或者年份，那麼日期對象會自動完成這種轉換。
####比較日期
日期對象也可用於比較兩個日期。
下面的代碼將當前日期與 2008 年 8 月 9 日做了比較：
```
var myDate=new Date();
myDate.setFullYear(2008,8,9);

var today = new Date();

if (myDate>today)
{
alert("Today is before 9th August 2008");
}
else
{
alert("Today is after 9th August 2008");
}
```
* getTime() 返回從 1970 年 1 月 1 日至今的毫秒數。
`var d=new Date();`
* 如何使用 setFullYear() 設置具體的日期。
```
var d = new Date()
d.setFullYear(1992,10,3)
```
* 如何使用 toUTCString() 將當日的日期（根據 UTC）轉換為字符串。
```
var d = new Date(); //Sat Mar 11 2017 16:11:14 GMT+0800 (CST)
d.toUTCString(); //Sat, 11 Mar 2017 08:11:14 GMT
```
* 如何使用 getDay() 和數組來顯示星期，而不僅僅是數字。

```html
<html>
<body>

<script type="text/javascript">

var d=new Date()
var weekday=new Array(7)
weekday[0]="星期日"
weekday[1]="星期一"
weekday[2]="星期二"
weekday[3]="星期三"
weekday[4]="星期四"
weekday[5]="星期五"
weekday[6]="星期六"

document.write("今天是" + weekday[d.getDay()])

</script>

</body>
</html>
```
* 如何在網頁上顯示一個鐘錶。

```html
<html>
<head>
<script type="text/javascript">
function startTime()
{
var today=new Date()
var h=today.getHours()
var m=today.getMinutes()
var s=today.getSeconds()
// add a zero in front of numbers<10
m=checkTime(m)
s=checkTime(s)
document.getElementById('txt').innerHTML=h+":"+m+":"+s
t=setTimeout('startTime()',500)
}

function checkTime(i)
{
if (i<10)
{i="0" + i}
return i
}
</script>
</head>

<body onload="startTime()">
<div id="txt"></div>
</body>
</html>
```

數組對象的作用是：使用單獨的變量名來存儲一系列的值。
###JavaScript Array（數組）
####定義數組
數組對象用來在單獨的變量名中存儲一系列的值。
我們使用關鍵詞 new 來創建數組對象。下面的代碼定義了一個名為 myArray 的數組對象：
`var myArray=new Array()`
有兩種向數組賦值的方法（你可以添加任意多的值，就像你可以定義你需要的任意多的變量一樣）。
```
1:
var mycars=new Array()
mycars[0]="Saab"
mycars[1]="Volvo"
mycars[2]="BMW"
也可以使用一個整數自變量來控制數組的容量：
var mycars=new Array(3)
mycars[0]="Saab"
mycars[1]="Volvo"
mycars[2]="BMW"
2:
var mycars=new Array("Saab","Volvo","BMW")
```
注意：如果你需要在數組內指定數值或者邏輯值，那麼變量類型應該是數值變量或者布爾變量，而不是字符變量。
####訪問數組
通過指定數組名以及索引號碼，你可以訪問某個特定的元素。
下面是代碼行：
`document.write(mycars[0])`
下面是輸出：
`Saab`
#####修改已有數組中的值
如需修改已有數組中的值，只要向指定下標號添加一個新值即可：
`mycars[0]="Opel";`
現在，以上代碼：
`document.write(mycars[0]);`
將輸出：
`Opel`

* 使用 for...in 聲明來循環輸出數組中的元素。

```
var x
var mycars = new Array()
mycars[0] = "Saab"
mycars[1] = "Volvo"
mycars[2] = "BMW"

for (x in mycars)
{
  mycars[x]
}
```
* 如何使用 concat() 方法來合併兩個數組。
  
```
var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

var arr2 = new Array(3)
arr2[0] = "James"
arr2[1] = "Adrew"
arr2[2] = "Martin"

arr.concat(arr2)
```
* 如何使用 join() 方法將數組的所有元素組成一個字符串。

```
var arr = new Array(3);
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"

arr.join()  //George,John,Thomas
arr.join(".")  //George.John.Thomas
```
* 如何使用 sort() 方法從字面上對數組進行排序。

```
var arr = new Array(6)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"
arr[3] = "James"
arr[4] = "Adrew"
arr[5] = "Martin"

arr.sort()  //Adrew,George,James,John,Martin,Thomas
```
  
* 如何使用 sort() 方法從數值上對數組進行排序。

```html
function sortNumber(a, b)
{
  return a - b
}
var arr = new Array(6)
arr[0] = "10"
arr[1] = "5"
arr[2] = "40"
arr[3] = "25"
arr[4] = "1000"
arr[5] = "1"
arr.sort(sortNumber)  //1,5,10,25,40,1000
```

Boolean（邏輯）對象用於將非邏輯值轉換為邏輯值（true 或者 false）。
###JavaScript Boolean（邏輯）
####Boolean 對象
您可以將 Boolean 對象理解為一個產生邏輯值的對象包裝器。
Boolean（邏輯）對象用於將非邏輯值轉換為邏輯值（true 或者 false）。
####創建 Boolean 對象
使用關鍵詞 new 來定義 Boolean 對象。下面的代碼定義了一個名為 myBoolean 的邏輯對象：
`var myBoolean=new Boolean()`
注釋：如果邏輯對象無初始值或者其值為 `0、-0、null、""、false、undefined` 或者 NaN，那麼對象的值為 false。否則，其值為 true（即使當自變量為字符串 "false" 時）！
下面的所有的代碼行均會創建初始值為 false 的 Boolean 對象。
```
var myBoolean=new Boolean();
var myBoolean=new Boolean(0);
var myBoolean=new Boolean(null);
var myBoolean=new Boolean("");
var myBoolean=new Boolean(false);
var myBoolean=new Boolean(NaN);
```
下面的所有的代碼行均會創初始值為 true 的 Boolean 對象：
```
var myBoolean=new Boolean(1);
var myBoolean=new Boolean(true);
var myBoolean=new Boolean("true");
var myBoolean=new Boolean("false");
var myBoolean=new Boolean("Bill Gates");
```
* 檢查邏輯對象是 true 還是 false。

```html
<html>
<body>

<script type="text/javascript">
var b1=new Boolean( 0)
var b2=new Boolean(1)
var b3=new Boolean("")
var b4=new Boolean(null)
var b5=new Boolean(NaN)
var b6=new Boolean("false")

document.write("0 是邏輯的 "+ b1 +"<br />")
document.write("1 是邏輯的 "+ b2 +"<br />")
document.write("空字符串是邏輯的 "+ b3 + "<br />")
document.write("null 是邏輯的 "+ b4+ "<br />")
document.write("NaN 是邏輯的 "+ b5 +"<br />")
document.write("字符串 'false' 是邏輯的 "+ b6 +"<br />")
</script>

</body>
</html>
```

Math（算數）對象的作用是：執行常見的算數任務。
###JavaScript Math（算數）
####Math 對象
Math（算數）對象的作用是：執行普通的算數任務。
Math 對象提供多種算數值類型和函數。無需在使用這個對象之前對它進行定義。
####算數值
JavaScript 提供 8 種可被 Math 對象訪問的算數值：

* 常數
* 圓周率
* 2 的平方根
* 1/2 的平方根
* 2 的自然對數
* 10 的自然對數
* 以 2 為底的 e 的對數
* 以 10 為底的 e 的對數
這是在 Javascript 中使用這些值的方法：（與上面的算數值一一對應）

* Math.E
* Math.PI
* Math.SQRT2
* Math.SQRT1_2
* Math.LN2
* Math.LN10
* Math.LOG2E
* Math.LOG10E
####算數方法
除了可被 Math 對象訪問的算數值以外，還有幾個函數（方法）可以使用。
函數（方法）實例：
下面的例子使用了 Math 對象的 round 方法對一個數進行四捨五入。
`document.write(Math.round(4.7))`
上面的代碼輸出為：
`5`
下面的例子使用了 Math 對象的 random() 方法來返回一個介於 0 和 1 之間的隨機數：
`document.write(Math.random())`
上面的代碼輸出為：
`0.9370844220218102`
下面的例子使用了 Math 對象的 floor() 方法和 random() 來返回一個介於 0 和 10 之間的隨機數：
`document.write(Math.floor(Math.random()*11)) `
上面的代碼輸出為：
`3`

* 如何使用 max() 來返回兩個給定的數中的較大的數。

```
Math.max(5,7)  //7
Math.max(-3,5)  //5
Math.max(-3,-5) //-3
Math.max(7.25,7.30)  //7.3
```

* 如何使用 min() 來返回兩個給定的數中的較小的數。  

RegExp 對象用於規定在文本中檢索的內容。
###JavaScript RegExp
####什麼是 RegExp？
RegExp 是正則表達式的縮寫。
當您檢索某個文本時，可以使用一種模式來描述要檢索的內容。RegExp 就是這種模式。
簡單的模式可以是一個單獨的字符。
更複雜的模式包括了更多的字符，並可用於解析、格式檢查、替換等等。
您可以規定字符串中的檢索位置，以及要檢索的字符類型，等等。
####定義 RegExp
RegExp 對象用於存儲檢索模式。
通過 new 關鍵詞來定義 RegExp 對象。以下代碼定義了名為 patt1 的 RegExp 對象，其模式是 "e"：
`var patt1=new RegExp("e");`
當您使用該 RegExp 對象在一個字符串中檢索時，將尋找的是字符 "e"。
####RegExp 對象的方法
RegExp 對象有 3 個方法：test()、exec() 以及 compile()。
#####test()
test() 方法檢索字符串中的指定值。返回值是 true 或 false。
例子：
```
var patt1=new RegExp("e");

document.write(patt1.test("The best things in life are free")); 
```
由於該字符串中存在字母 "e"，以上代碼的輸出將是：
`true`

#####exec()
exec() 方法檢索字符串中的指定值。返回值是被找到的值。如果沒有發現匹配，則返回 null。
例子 1：
```
var patt1=new RegExp("e");

document.write(patt1.exec("The best things in life are free")); 
```
由於該字符串中存在字母 "e"，以上代碼的輸出將是：
`e`

例子 2：
您可以向 RegExp 對象添加第二個參數，以設定檢索。例如，如果需要找到所有某個字符的所有存在，則可以使用 "g" 參數 ("global")。
在使用 "g" 參數時，exec() 的工作原理如下：
找到第一個 "e"，並存儲其位置
如果再次運行 exec()，則從存儲的位置開始檢索，並找到下一個 "e"，並存儲其位置
```
var patt1=new RegExp("e","g");
do
{
result=patt1.exec("The best things in life are free");
document.write(result);
}
while (result!=null) 
```
由於這個字符串中 6 個 "e" 字母，代碼的輸出將是：
`eeeeeenull`

#####compile()
compile() 方法用於改變 RegExp。
compile() 既可以改變檢索模式，也可以添加或刪除第二個參數。
例子：
```
var patt1=new RegExp("e");

document.write(patt1.test("The best things in life are free"));

patt1.compile("d");

document.write(patt1.test("The best things in life are free"));
```
由於字符串中存在 "e"，而沒有 "d"，以上代碼的輸出是：
`truefalse`
