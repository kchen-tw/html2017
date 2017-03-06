##什麼是語義元素？
語義元素清楚地向瀏覽器和開發者描述其意義。
非語義元素的例子：`<div>` 和 `<span>` - 無法提供關於其內容的信息。
語義元素的例子：`<form>`、`<table>` 以及 `<img>` - 清晰地定義其內容。

###HTML5 中新的語義元素
許多網站包含了指示導航、頁眉以及頁腳的 HTML 代碼，例如這些：`<div id="nav">` `<div class="header">` `<div id="footer">`。
HTML5 提供了定義頁面不同部分的新語義元素：
```html
<article>
<aside>
<details>
<figcaption>
<figure>
<footer>
<header>
<main>
<mark>
<nav>
<section>
<summary>
<time>
```

###HTML5 `<section>` 元素
`<section>` 元素定義文檔中的節。
根據 W3C 的 HTML 文獻：「節（section）是有主題的內容組，通常具有標題」。
可以將網站首頁劃分為簡介、內容、聯繫信息等節。
```html
<section>
   <h1>WWF</h1>
   <p>The World Wide Fund for Nature (WWF) is....</p>
</section> 
```

###HTML5 `<article>` 元素
`<article>` 元素規定獨立的自包含內容。
文檔有其自身的意義，並且可以獨立於網站其他內容進行閱讀。
`<article>` 元素的應用場景：
論壇
博客
新聞
```html
<article>
   <h1>What Does WWF Do?</h1>
   <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article> 
   ```

###巢狀的語義元素
在 HTML5 標準中，`<article>` 元素定義完整的相關元素自包含塊。
`<section>` 元素被定義為相關元素塊。
我們能夠使用該定義來決定如何嵌套元素嗎？不，我們不能！
在因特網上，您會發現 `<section>` 元素包含 `<article>` 元素的 HTML 頁面，還有 `<article>` 元素包含 `<sections>` 元素的頁面。
您還會發現 `<section>` 元素包含 `<section>` 元素，同時 `<article>` 元素包含 `<article>` 元素。

###HTML5 `<header>` 元素
`<header>` 元素為文檔或節規定頁眉。
`<header>` 元素應該被用作介紹性內容的容器。
一個文檔中可以有多個 `<header>` 元素。
下例為一篇文章定義了頁眉：
```html
<article>
   <header>
     <h1>What Does WWF Do?</h1>
     <p>WWF's mission:</p>
   </header>
   <p>WWF's mission is to stop the degradation of our planet's natural environment,
  and build a future in which humans live in harmony with nature.</p>
</article> 
```

###HTML5 `<footer>` 元素
`<footer>` 元素為文檔或節規定頁腳。
`<footer>` 元素應該提供有關其包含元素的信息。
頁腳通常包含文檔的作者、版權信息、使用條款鏈接、聯繫信息等等。
您可以在一個文檔中使用多個 `<footer>` 元素。
```html
<footer>
   <p>Posted by: Hege Refsnes</p>
   <p>Contact information: <a href="mailto:someone@example.com">
  someone@example.com</a>.</p>
</footer> 
```

###HTML5 `<nav>` 元素
`<nav>` 元素定義導航鏈接集合。
`<nav>` 元素旨在定義大型的導航鏈接塊。不過，並非文檔中所有鏈接都應該位於 `<nav>` 元素中！
```html
<nav>
<a href="/html/">HTML</a> |
<a href="/css/">CSS</a> |
<a href="/js/">JavaScript</a> |
<a href="/jquery/">jQuery</a>
</nav> 
```

###HTML5 `<aside>` 元素
`<aside>` 元素頁面主內容之外的某些內容（比如側欄）。
aside 內容應該與周圍內容相關。
```html
<p>My family and I visited The Epcot center this summer.</p>

<aside>
   <h4>Epcot Center</h4>
   <p>The Epcot Center is a theme park in Disney World, Florida.</p>
</aside> 
   ```

###HTML5 `<figure>` 和 `<figcaption>` 元素
在書籍和報紙中，與圖片搭配的標題很常見。
標題（caption）的作用是為圖片添加可見的解釋。
通過 HTML5，圖片和標題能夠被組合在 `<figure>` 元素中：
```html
<figure>
   <img src="pic_mountain.jpg" alt="The Pulpit Rock" width="304" height="228">
   <figcaption>Fig1. - The Pulpit Pock, Norway.</figcaption>
</figure> 
   ```
   
