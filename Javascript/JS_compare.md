比較和邏輯運算符用於測試 true 或 false。
##比較運算符
比較運算符在邏輯語句中使用，以測定變量或值是否相等。
給定 x=5，下面的表格解釋了比較運算符：

|運算符|	描述|	例子|
|- - -| - - -|- - -|
|==	|等於|	x==8 為 false|
|===	|全等（值和類型）	|x===5 為 true；x==="5" 為 false|
|!=	|不等於	|x!=8 為 true|
|>	|大於	|x>8 為 false|
|<	|小於	|x`<`8 為 true|
|>=	|大於或等於|	x>=8 為 false|
|`<=`	|小於或等於|	x`<=`8 為 true|
###如何使用
可以在條件語句中使用比較運算符對值進行比較，然後根據結果來採取行動：
`if (age<18) document.write("Too young");`
###邏輯運算符
邏輯運算符用於測定變量或值之間的邏輯。
給定 x=6 以及 y=3，下表解釋了邏輯運算符：

|運算符|	描述	|例子|
|- - -|- - -|- - -|
|&&	|and	|(x < 10 && y > 1) 為 true|
| \|\|	|or	|(x==5 \|\| y==5) 為 false|
|!	|not	|!(x==y) 為 true|
###條件運算符
JavaScript 還包含了基於某些條件對變量進行賦值的條件運算符。
語法
`variablename=(condition)?value1:value2 `
例子
`greeting=(visitor=="PRES")?"Dear President ":"Dear ";`
如果變量 visitor 中的值是 "PRES"，則向變量 greeting 賦值 "Dear President "，否則賦值 "Dear"。