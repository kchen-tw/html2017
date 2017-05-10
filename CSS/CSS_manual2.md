##CSS 网络安全字体组合
###常用的字体组合
font-family 属性应该使用若干种字体名称作为回退系统，以确保浏览器/操作系统之间的最大兼容性。如果浏览器不支持第一个字体，则会尝试下一个。

请以您喜欢的字体开始，并以通用字体系列结束，以便使浏览器在通用系统中挑选相似的字体，如果没有其他字体可用的话：

实例

`p{font-family:'Times New Roman', Times, serif}`

下面是最常用的字体组合，根据通用系统进行汇总：

###Serif 字体

####font-family
* Georgia, serif
* 'Palatino Linotype', 'Book Antiqua', Palatino, serif	
* 'Times New Roman', Times, serif	

###Sans-Serif 字体

####font-family	示例文本
* Arial, Helvetica, sans-serif	
* 'Arial Black', Gadget, sans-serif	
* 'Comic Sans MS', cursive, sans-serif	
* Impact, Charcoal, sans-serif	
* 'Lucida Sans Unicode', 'Lucida Grande', sans-serif	
* Tahoma, Geneva, sans-serif	
* 'Trebuchet MS', Helvetica, sans-serif	
* Verdana, Geneva, sans-serif	

###Monospace 字体
####font-family	示例文本
* 'Courier New', Courier, monospace	
* 'Lucida Console', Monaco, monospace	

___

##CSS 单位
尺寸

单位|	描述
:--:|:--:
%|	百分比
in|	英寸
cm|	厘米
mm|	毫米
em|	1em 等于当前的字体尺寸。<br>2em 等于当前字体尺寸的两倍。<br>例如，如果某元素以 12pt 显示，那么 2em 是24pt。<br>在 CSS 中，em 是非常有用的单位，因为它可以自动适应用户所使用的字体。
ex|	一个 ex 是一个字体的 x-height。 (x-height 通常是字体尺寸的一半。)
pt|	磅 (1 pt 等于 1/72 英寸)
pc|	12 点活字 (1 pc 等于 12 点)
px|	像素 (计算机屏幕上的一个点)

颜色

单位|	描述
:--:|:--:
(颜色名)	|颜色名称 (比如 red)
rgb(x,x,x)|	RGB 值 (比如 rgb(255,0,0))
rgb(x%, x%, x%)	|RGB 百分比值 (比如 rgb(100%,0%,0%))
#rrggbb	|十六进制数 (比如 #ff0000)

___

##CSS 合法颜色值

###CSS 颜色
可以用以下方法来规定 CSS 中的颜色：
* 十六进制色
* RGB 颜色
* RGBA 颜色
* HSL 颜色
* HSLA 颜色
* 预定义/跨浏览器颜色名

###十六进制颜色
所有浏览器都支持十六进制颜色值。
十六进制颜色是这样规定的：#RRGGBB，其中的 RR（红色）、GG（绿色）、BB（蓝色）十六进制整数规定了颜色的成分。所有值必须介于 0 与 FF 之间。
举例说，#0000ff 值显示为蓝色，这是因为蓝色成分被设置为最高值（ff），而其他成分被设置为 0。

实例
```css
p
{
background-color:#0000ff;
}
```

###RGB 颜色
所有浏览器都支持 RGB 颜色值。
RGB 颜色值是这样规定的：rgb(red, green, blue)。每个参数 (red、green 以及 blue) 定义颜色的强度，可以是介于 0 与 255 之间的整数，或者是百分比值（从 0% 到 100%）。
举例说，rgb(0,0,255) 值显示为蓝色，这是因为 blue 参数被设置为最高值（255），而其他被设置为 0。
同样地，下面的值定义了相同的颜色：rgb(0,0,255) 和 rgb(0%,0%,100%)。

实例

```css
p
{
background-color:rgb(255,0,0);
}
```

###RGBA 颜色
RGBA 颜色值得到以下浏览器的支持：IE9+、Firefox 3+、Chrome、Safari 以及 Opera 10+。
RGBA 颜色值是 RGB 颜色值的扩展，带有一个 alpha 通道 - 它规定了对象的不透明度。
RGBA 颜色值是这样规定的：rgba(red, green, blue, alpha)。alpha 参数是介于 0.0（完全透明）与 1.0（完全不透明）的数字。

实例

```css
p
{
background-color:rgba(255,0,0,0.5);
}
```

###HSL 颜色
HSL 颜色值得到以下浏览器的支持：IE9+、Firefox、Chrome、Safari 以及 Opera 10+。
HSL 指的是 hue（色调）、saturation（饱和度）、lightness（亮度） - 表示颜色柱面坐标表示法。
HSL 颜色值是这样规定的：hsl(hue, saturation, lightness)。
Hue 是色盘上的度数（从 0 到 360） - 0 (或 360) 是红色，120 是绿色，240 是蓝色。Saturation 是百分比值；0% 意味着灰色，而 100% 是全彩。Lightness 同样是百分比值；0% 是黑色，100% 是白色。

实例

```css
p
{
background-color:hsl(120,65%,75%);
}
```

###HSLA 颜色
HSLA 颜色值得到以下浏览器的支持：IE9+、Firefox 3+、Chrome、Safari 以及 Opera 10+。
HSLA 颜色值是 HSL 颜色值的扩展，带有一个 alpha 通道 - 它规定了对象的不透明度。
HSLA 颜色值是这样规定的：hsla(hue, saturation, lightness, alpha)，其中的 alpha 参数定义不透明度。alpha 参数是介于 0.0（完全透明）与 1.0（完全不透明）的数字。

实例

```css
p
{
background-color:hsla(120,65%,75%,0.3);
}
```

___

##CSS 颜色十六进制值

颜色名|	十六进制颜色值
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