##CSS 網絡安全字體組合
###常用的字體組合
font-family 屬性應該使用若干種字體名稱作為回退系統，以確保瀏覽器/操作系統之間的最大兼容性。如果瀏覽器不支持第一個字體，則會嘗試下一個。

請以您喜歡的字體開始，並以通用字體系列結束，以便使瀏覽器在通用系統中挑選相似的字體，如果沒有其他字體可用的話：

實例

`p{font-family:'Times New Roman', Times, serif}`

下面是最常用的字體組合，根據通用系統進行匯總：

###Serif 字體

####font-family
* Georgia, serif
* 'Palatino Linotype', 'Book Antiqua', Palatino, serif	
* 'Times New Roman', Times, serif	

###Sans-Serif 字體

####font-family	示例文本
* Arial, Helvetica, sans-serif	
* 'Arial Black', Gadget, sans-serif	
* 'Comic Sans MS', cursive, sans-serif	
* Impact, Charcoal, sans-serif	
* 'Lucida Sans Unicode', 'Lucida Grande', sans-serif	
* Tahoma, Geneva, sans-serif	
* 'Trebuchet MS', Helvetica, sans-serif	
* Verdana, Geneva, sans-serif	

###Monospace 字體
####font-family	示例文本
* 'Courier New', Courier, monospace	
* 'Lucida Console', Monaco, monospace	

___

##CSS 單位
尺寸

單位|	描述
:--:|:--:
%|	百分比
in|	英吋
cm|	釐米
mm|	毫米
em|	1em 等於當前的字體尺寸。<br>2em 等於當前字體尺寸的兩倍。<br>例如，如果某元素以 12pt 顯示，那麼 2em 是24pt。<br>在 CSS 中，em 是非常有用的單位，因為它可以自動適應用戶所使用的字體。
ex|	一個 ex 是一個字體的 x-height。 (x-height 通常是字體尺寸的一半。)
pt|	磅 (1 pt 等於 1/72 英吋)
pc|	12 點活字 (1 pc 等於 12 點)
px|	像素 (計算機屏幕上的一個點)

顏色

單位|	描述
:--:|:--:
(顏色名)	|顏色名稱 (比如 red)
rgb(x,x,x)|	RGB 值 (比如 rgb(255,0,0))
rgb(x%, x%, x%)	|RGB 百分比值 (比如 rgb(100%,0%,0%))
#rrggbb	|十六進制數 (比如 #ff0000)

___

##CSS 合法顏色值

###CSS 顏色
可以用以下方法來規定 CSS 中的顏色：
* 十六進制色
* RGB 顏色
* RGBA 顏色
* HSL 顏色
* HSLA 顏色
* 預定義/跨瀏覽器顏色名

###十六進制顏色
所有瀏覽器都支持十六進制顏色值。
十六進制顏色是這樣規定的：#RRGGBB，其中的 RR（紅色）、GG（綠色）、BB（藍色）十六進制整數規定了顏色的成分。所有值必須介於 0 與 FF 之間。
舉例說，#0000ff 值顯示為藍色，這是因為藍色成分被設置為最高值（ff），而其他成分被設置為 0。

實例
```css
p
{
background-color:#0000ff;
}
```

###RGB 顏色
所有瀏覽器都支持 RGB 顏色值。
RGB 顏色值是這樣規定的：rgb(red, green, blue)。每個參數 (red、green 以及 blue) 定義顏色的強度，可以是介於 0 與 255 之間的整數，或者是百分比值（從 0% 到 100%）。
舉例說，rgb(0,0,255) 值顯示為藍色，這是因為 blue 參數被設置為最高值（255），而其他被設置為 0。
同樣地，下面的值定義了相同的顏色：rgb(0,0,255) 和 rgb(0%,0%,100%)。

實例

```css
p
{
background-color:rgb(255,0,0);
}
```

###RGBA 顏色
RGBA 顏色值得到以下瀏覽器的支持：IE9+、Firefox 3+、Chrome、Safari 以及 Opera 10+。
RGBA 顏色值是 RGB 顏色值的擴展，帶有一個 alpha 通道 - 它規定了對象的不透明度。
RGBA 顏色值是這樣規定的：rgba(red, green, blue, alpha)。alpha 參數是介於 0.0（完全透明）與 1.0（完全不透明）的數字。

實例

```css
p
{
background-color:rgba(255,0,0,0.5);
}
```

###HSL 顏色
HSL 顏色值得到以下瀏覽器的支持：IE9+、Firefox、Chrome、Safari 以及 Opera 10+。
HSL 指的是 hue（色調）、saturation（飽和度）、lightness（亮度） - 表示顏色柱面坐標表示法。
HSL 顏色值是這樣規定的：hsl(hue, saturation, lightness)。
Hue 是色盤上的度數（從 0 到 360） - 0 (或 360) 是紅色，120 是綠色，240 是藍色。Saturation 是百分比值；0% 意味著灰色，而 100% 是全彩。Lightness 同樣是百分比值；0% 是黑色，100% 是白色。

實例

```css
p
{
background-color:hsl(120,65%,75%);
}
```

###HSLA 顏色
HSLA 顏色值得到以下瀏覽器的支持：IE9+、Firefox 3+、Chrome、Safari 以及 Opera 10+。
HSLA 顏色值是 HSL 顏色值的擴展，帶有一個 alpha 通道 - 它規定了對象的不透明度。
HSLA 顏色值是這樣規定的：hsla(hue, saturation, lightness, alpha)，其中的 alpha 參數定義不透明度。alpha 參數是介於 0.0（完全透明）與 1.0（完全不透明）的數字。

實例

```css
p
{
background-color:hsla(120,65%,75%,0.3);
}
```

___

##CSS 顏色十六進制值

顏色名|	十六進制顏色值
:--:|:--:
Black	|#000000	 
Navy	|#000080	 
DarkBlue|	#00008B	 
MediumBlue|	#0000CD	 
Blue	|#0000FF	 
DarkGreen|	#006400	 
Green	|#008000	 
Teal	|#008080	 
DarkCyan|	#008B8B	 
DeepSkyBlue|	#00BFFF	 
DarkTurquoise|	#00CED1	 
MediumSpringGreen|	#00FA9A	 
Lime	|#00FF00	 
SpringGreen|	#00FF7F	 
Aqua|	#00FFFF	 
Cyan|	#00FFFF	 
MidnightBlue|	#191970	 
DodgerBlue	|#1E90FF	 
LightSeaGreen	|#20B2AA	 
ForestGreen|	#228B22	 
SeaGreen|	#2E8B57	 
DarkSlateGray|	#2F4F4F	 
LimeGreen|	#32CD32	 
MediumSeaGreen|	#3CB371	 
Turquoise|	#40E0D0	 
RoyalBlue|	#4169E1	 
SteelBlue|	#4682B4	 
DarkSlateBlue|	#483D8B	 
MediumTurquoise|	#48D1CC	 
Indigo	|#4B0082	 
DarkOliveGreen|	#556B2F	 
CadetBlue	|#5F9EA0	 
CornflowerBlue	|#6495ED	 
MediumAquaMarine|	#66CDAA	 
DimGray	|#696969	 
DimGrey	|#696969	 
SlateBlue|	#6A5ACD	 
OliveDrab|	#6B8E23	 
SlateGray|	#708090	 
LightSlateGray|	#778899	 
MediumSlateBlue|	#7B68EE	 
LawnGreen	|#7CFC00	 
Chartreuse	|#7FFF00	 
Aquamarine	|#7FFFD4	 
Maroon|	#800000	 
Purple	|#800080	 
Olive	|#808000	 
Gray	|#808080	 
SkyBlue	|#87CEEB	 
LightSkyBlue|	#87CEFA	 
BlueViolet|	#8A2BE2	 
DarkRed|	#8B0000	 
DarkMagenta|	#8B008B	 
SaddleBrown|	#8B4513	 
DarkSeaGreen|	#8FBC8F	 
LightGreen	|#90EE90	 
MediumPurple	|#9370DB	 
DarkViolet|	#9400D3	 
PaleGreen|	#98FB98	 
DarkOrchid|	#9932CC	 
YellowGreen|	#9ACD32	 
Sienna|	#A0522D	 
Brown	#A52A2A	 
DarkGray|	#A9A9A9	 
LightBlue|	#ADD8E6	 
GreenYellow|	#ADFF2F	 
PaleTurquoise|	#AFEEEE	 
LightSteelBlue|	#B0C4DE	 
PowderBlue|	#B0E0E6	 
FireBrick|	#B22222	 
DarkGoldenRod|	#B8860B	 
MediumOrchid|	#BA55D3	 
RosyBrown|	#BC8F8F	 
DarkKhaki|	#BDB76B	 
Silver	|#C0C0C0	 
MediumVioletRed|	#C71585	 
IndianRed	|#CD5C5C	 
Peru|	#CD853F	 
Chocolate|	#D2691E	 
Tan	|#D2B48C	 
LightGray|	#D3D3D3	 
Thistle	|#D8BFD8	 
Orchid	|#DA70D6	 
GoldenRod|	#DAA520	 
PaleVioletRed|	#DB7093	 
Crimson|	#DC143C	 
Gainsboro|	#DCDCDC	 
Plum|	#DDA0DD	 
BurlyWood|	#DEB887	 
LightCyan|	#E0FFFF	 
Lavender|	#E6E6FA	 
DarkSalmon|	#E9967A	 
Violet|	#EE82EE	 
PaleGoldenRod|	#EEE8AA	 
LightCoral|	#F08080	 
Khaki|	#F0E68C	 
AliceBlue|	#F0F8FF	 
HoneyDew|	#F0FFF0	 
Azure|	#F0FFFF	 
SandyBrown|	#F4A460	 
Wheat|	#F5DEB3	 
Beige|	#F5F5DC	 
WhiteSmoke|	#F5F5F5	 
MintCream|	#F5FFFA	 
GhostWhite|	#F8F8FF	 
Salmon|	#FA8072	 
AntiqueWhite|	#FAEBD7	 
Linen|	#FAF0E6	 
LightGoldenRodYellow|	#FAFAD2	 
OldLace|	#FDF5E6	 
Red	|#FF0000	 
Fuchsia	|#FF00FF	 
Magenta	|#FF00FF	 
DeepPink|	#FF1493	 
OrangeRed|	#FF4500	 
Tomato	|#FF6347	 
HotPink	|#FF69B4	 
Coral	|#FF7F50	 
Darkorange|	#FF8C00	 
LightSalmon|	#FFA07A	 
Orange|	#FFA500	 
LightPink|	#FFB6C1	 
Pink	|#FFC0CB	 
Gold	|#FFD700	 
PeachPuff|	#FFDAB9	 
NavajoWhite|	#FFDEAD	 
Moccasin	|#FFE4B5	 
Bisque|	#FFE4C4	 
MistyRose|	#FFE4E1	 
BlanchedAlmond|	#FFEBCD	 
PapayaWhip|	#FFEFD5	 
LavenderBlush|	#FFF0F5	 
SeaShell	|#FFF5EE	 
Cornsilk	|#FFF8DC	 
LemonChiffon|	#FFFACD	 
FloralWhite|	#FFFAF0	 
Snow|	#FFFAFA	 
Yellow|	#FFFF00	 
LightYellow|	#FFFFE0	 
Ivory|	#FFFFF0	 
White|	#FFFFFF