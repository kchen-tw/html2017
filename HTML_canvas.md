##什麼是 Canvas？
HTML5 的 canvas 元素使用 JavaScript 在網頁上繪製圖像。
畫布是一個矩形區域，您可以控制其每一像素。
canvas 擁有多種繪制路徑、矩形、圓形、字符以及添加圖像的方法。

###創建 Canvas 元素
向 HTML5 頁面添加 canvas 元素。
規定元素的 id、寬度和高度：
`<canvas id="myCanvas" width="200" height="100"></canvas>`

###通過 JavaScript 來繪制
canvas 元素本身是沒有繪圖能力的。所有的繪制工作必須在 JavaScript 內部完成：
```html
<script type="text/javascript">
var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
cxt.fillStyle="#FF0000";
cxt.fillRect(0,0,150,75);
</script>
```

####JavaScript 使用 id 來尋找 canvas 元素：
`var c=document.getElementById("myCanvas");`
然後，創建 context 對象：
`var cxt=c.getContext("2d");` 
getContext("2d") 對象是內建的 HTML5 對象，擁有多種繪制路徑、矩形、圓形、字符以及添加圖像的方法。
下面的兩行代碼繪制一個紅色的矩形：
`cxt.fillStyle="#FF0000";`
`cxt.fillRect(0,0,150,75);` 
fillStyle 方法將其染成紅色，fillRect 方法規定了形狀、位置和尺寸。

####理解坐標
上面的 fillRect 方法擁有參數 (0,0,150,75)。
意思是：在畫布上繪制 150x75 的矩形，從左上角開始 (0,0)。

###實例 - 線條
通過指定從何處開始，在何處結束，來繪制一條線：
JavaScript 代碼：
```
<script type="text/javascript">

var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
cxt.moveTo(10,10);
cxt.lineTo(150,50);
cxt.lineTo(10,50);
cxt.stroke();

</script>
```
```
canvas 元素：
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #c3c3c3;">
Your browser does not support the canvas element.
</canvas>
```

###例 - 圓形
通過規定尺寸、顏色和位置，來繪制一個圓：
JavaScript 代碼：
```
<script type="text/javascript">

var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
cxt.fillStyle="#FF0000";
cxt.beginPath();
cxt.arc(70,18,15,0,Math.PI*2,true);
cxt.closePath();
cxt.fill();
</script>
```
canvas 元素：
````
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #c3c3c3;">
Your browser does not support the canvas element.
</canvas>
```


###實例 - 漸變
使用您指定的顏色來繪制漸變背景：
JavaScript 代碼：
```
<script type="text/javascript">

var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
var grd=cxt.createLinearGradient(0,0,175,50);
grd.addColorStop(0,"#FF0000");
grd.addColorStop(1,"#00FF00");
cxt.fillStyle=grd;
cxt.fillRect(0,0,175,50);

</script>
```
canvas 元素：
```
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #c3c3c3;">
Your browser does not support the canvas element.
</canvas>
```

###實例 - 圖像
把一幅圖像放置到畫布上：
JavaScript 代碼：
```
<script type="text/javascript">

var c=document.getElementById("myCanvas");
var cxt=c.getContext("2d");
var img=new Image()
img.src="flower.png"
cxt.drawImage(img,0,0);

</script>
```
canvas 元素：
```
<canvas id="myCanvas" width="200" height="100" style="border:1px solid #c3c3c3;">
Your browser does not support the canvas element.
</canvas>
```
