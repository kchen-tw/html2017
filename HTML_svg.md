##什麼是SVG？
SVG 指可伸縮矢量圖形 (Scalable Vector Graphics)
SVG 用於定義用於網絡的基於矢量的圖形
SVG 使用 XML 格式定義圖形
SVG 圖像在放大或改變尺寸的情況下其圖形質量不會有損失
SVG 是萬維網聯盟的標準
SVG 的優勢

####與其他圖像格式相比（比如 JPEG 和 GIF），使用 SVG 的優勢在於：
SVG 圖像可通過文本編輯器來創建和修改
SVG 圖像可被搜索、索引、腳本化或壓縮
SVG 是可伸縮的
SVG 圖像可在任何的分辨率下被高質量地打印
SVG 可在圖像質量不下降的情況下被放大

  ####瀏覽器支持
Internet Explorer 9、Firefox、Opera、Chrome 以及 Safari 支持內聯 SVG。
  
###把 SVG 直接嵌入 HTML 頁面
在 HTML5 中，您能夠將 SVG 元素直接嵌入 HTML 頁面中：
```html
<!DOCTYPE html>
<html>
<body>

<svg xmlns="http://www.w3.org/2000/svg" version="1.1" height="190">
  <polygon points="100,10 40,180 190,60 10,60 160,180"
  style="fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;" />
</svg>

</body>
</html>
```

<hr>

Canvas 和 SVG 都允許您在瀏覽器中創建圖形，但是它們在根本上是不同的。
####SVG
SVG 是一種使用 XML 描述 2D 圖形的語言。
SVG 基於 XML，這意味著 SVG DOM 中的每個元素都是可用的。您可以為某個元素附加 JavaScript 事件處理器。
在 SVG 中，每個被繪制的圖形均被視為對象。如果 SVG 對象的屬性發生變化，那麼瀏覽器能夠自動重現圖形。
####Canvas
Canvas 通過 JavaScript 來繪制 2D 圖形。
Canvas 是逐像素進行渲染的。
在 canvas 中，一旦圖形被繪制完成，它就不會繼續得到瀏覽器的關注。如果其位置發生變化，那麼整個場景也需要重新繪制，包括任何或許已被圖形覆蓋的對象。

####Canvas 與 SVG 的比較
下表列出了 canvas 與 SVG 之間的一些不同之處。
#####Canvas
依賴分辨率
不支持事件處理器
弱的文本渲染能力
能夠以 .png 或 .jpg 格式保存結果圖像
最適合圖像密集型的遊戲，其中的許多對象會被頻繁重繪
#####SVG
不依賴分辨率
支持事件處理器
最適合帶有大型渲染區域的應用程序（比如谷歌地圖）
複雜度高會減慢渲染速度（任何過度使用 DOM 的應用都不快）
不適合遊戲應用