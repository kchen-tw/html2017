字符串、數字、布爾、數組、對象、Null、Undefined
###JavaScript 擁有動態類型
JavaScript 擁有動態類型。這意味著相同的變量可用作不同的類型：
```
var x                // x 為 undefined
var x = 6;           // x 為數字
var x = "Bill";      // x 為字符串
```
###JavaScript 字符串
字符串是存儲字符（比如 "Bill Gates"）的變量。
字符串可以是引號中的任意文本。您可以使用單引號或雙引號：
```
var carname="Bill Gates";
var carname='Bill Gates';
```
您可以在字符串中使用引號，只要不匹配包圍字符串的引號即可：
```
var answer="Nice to meet you!";
var answer="He is called 'Bill'";
var answer='He is called "Bill"';
```

###JavaScript 數字
JavaScript 只有一種數字類型。數字可以帶小數點，也可以不帶：
```
var x1=34.00;      //使用小數點來寫
var x2=34;         //不使用小數點來寫
```
極大或極小的數字可以通過科學（指數）計數法來書寫：
```
var y=123e5;      // 12300000
var z=123e-5;     // 0.00123
```

###JavaScript 布爾
布爾（bool）只能有兩個值：true 或 false。
```
var x=true
var y=false
```
布爾常用在條件測試中。您將在本教程稍後的章節中學到更多關於條件測試的知識。
JavaScript 數組
下面的代碼創建名為 cars 的數組：
```
var cars=new Array();
cars[0]="Audi";
cars[1]="BMW";
cars[2]="Volvo";
```
或者 (condensed array):
`var cars=new Array("Audi","BMW","Volvo");`
或者 (literal array):
`var cars=["Audi","BMW","Volvo"];`

數組下標是基於零的，所以第一個項目是 [0]，第二個是 [1]，以此類推。

###JavaScript 對象
對象(object)由花括號分隔。在括號內部，對象的屬性以名稱和值對的形式 (name : value) 來定義。屬性由逗號分隔：
`var person={firstname:"Bill", lastname:"Gates", id:5566};`
上面例子中的對象 (person) 有三個屬性：firstname、lastname 以及 id。
空格和折行無關緊要。聲明可橫跨多行：
```
var person={
firstname : "Bill",
lastname  : "Gates",
id        :  5566
};
```
對象屬性有兩種尋址方式：
```
name=person.lastname;
name=person["lastname"];
```

###Undefined 和 Null
Undefined 這個值表示變量不含有值。
可以通過將變量的值設置為 null 來清空變量。
```
cars=null;
person=null;
```
###聲明變量類型
當您聲明新變量時，可以使用關鍵詞 "new" 來聲明其類型：
```
var carname=new String;
var x=      new Number;
var y=      new Boolean;
var cars=   new Array;
var person= new Object;
```
JavaScript 變量均為對象。當您聲明一個變量時，就創建了一個新的對象。



