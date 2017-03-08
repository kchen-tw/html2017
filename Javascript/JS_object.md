JavaScript 中的所有事物都是對象：字符串、數字、數組、日期，等等。
在 JavaScript 中，對象是擁有屬性和方法的數據。
###屬性和方法
屬性是與對象相關的值。
方法是能夠在對象上執行的動作。
舉例：汽車就是現實生活中的對象。
汽車的屬性：
```
car.name=Fiat

car.model=500

car.weight=850kg

car.color=white 
```
汽車的方法：
```
car.start()

car.drive()

car.brake()
```
汽車的屬性包括名稱、型號、重量、顏色等。
所有汽車都有這些屬性，但是每款車的屬性都不盡相同。
汽車的方法可以是啓動、駕駛、剎車等。
所有汽車都擁有這些方法，但是它們被執行的時間都不盡相同。
###JavaScript 中的對象
在 JavaScript 中，對象是數據（變量），擁有屬性和方法。
當您像這樣聲明一個 JavaScript 變量時：
`var txt = "Hello";`
您實際上已經創建了一個 JavaScript 字符串對象。字符串對象擁有內建的屬性 length。對於上面的字符串來說，length 的值是 5。字符串對象同時擁有若干個內建的方法。
屬性：
`txt.length=5`
方法：
```
txt.indexOf()

txt.replace()

txt.search()
```
提示：在面向對象的語言中，屬性和方法常被稱為對象的成員。

###創建 JavaScript 對象
JavaScript 中的幾乎所有事務都是對象：字符串、數字、數組、日期、函數，等等。
你也可以創建自己的對象。
本例創建名為 "person" 的對象，並為其添加了四個屬性：
```
person=new Object();
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";
```
創建新 JavaScript 對象有很多不同的方法，並且您還可以向已存在的對象添加屬性和方法。

###訪問對象的屬性
訪問對象屬性的語法是：
`objectName.propertyName`
本例使用 String 對象的 length 屬性來查找字符串的長度：
```
var message="Hello World!";
var x=message.length;
```
在以上代碼執行後，x 的值是：`12`
###訪問對象的方法
您可以通過下面的語法調用方法：
`objectName.methodName()`
這個例子使用 String 對象的 toUpperCase() 方法來把文本轉換為大寫：
```
var message="Hello world!";
var x=message.toUpperCase();
```
在以上代碼執行後，x 的值是：
`HELLO WORLD!`