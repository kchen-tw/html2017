##HTML5 地理定位

###定位用戶的位置
HTML5 Geolocation API 用於獲得用戶的地理位置。
鑒於該特性可能侵犯用戶的隱私，除非用戶同意，否則用戶位置信息是不可用的。
注釋：對於擁有 GPS 的設備，比如 iPhone，地理定位更加精確。

  ###HTML5 - 使用地理定位
請使用 getCurrentPosition() 方法來獲得用戶的位置。
下例是一個簡單的地理定位實例，可返回用戶位置的經度和緯度。
```html
<script>
var x=document.getElementById("demo");
function getLocation()
  {
  if (navigator.geolocation)
    {
    navigator.geolocation.getCurrentPosition(showPosition);
    }
  else{x.innerHTML="Geolocation is not supported by this browser.";}
  }
function showPosition(position)
  {
  x.innerHTML="Latitude: " + position.coords.latitude +
  "<br />Longitude: " + position.coords.longitude;
  }
</script>
```

例子解釋：
檢測是否支持地理定位
如果支持，則運行 getCurrentPosition() 方法。如果不支持，則向用戶顯示一段消息。
如果getCurrentPosition()運行成功，則向參數showPosition中規定的函數返回一個coordinates對象
showPosition() 函數獲得並顯示經度和緯度
上面的例子是一個非常基礎的地理定位腳本，不含錯誤處理。
####處理錯誤和拒絕
getCurrentPosition() 方法的第二個參數用於處理錯誤。它規定當獲取用戶位置失敗時運行的函數：
```
function showError(error)
  {
  switch(error.code)
    {
    case error.PERMISSION_DENIED:
      x.innerHTML="User denied the request for Geolocation."
      break;
    case error.POSITION_UNAVAILABLE:
      x.innerHTML="Location information is unavailable."
      break;
    case error.TIMEOUT:
      x.innerHTML="The request to get user location timed out."
      break;
    case error.UNKNOWN_ERROR:
      x.innerHTML="An unknown error occurred."
      break;
    }
  }
```
#####錯誤代碼：
Permission denied - 用戶不允許地理定位
Position unavailable - 無法獲取當前位置
Timeout - 操作超時
###在地圖中顯示結果
如需在地圖中顯示結果，您需要訪問可使用經緯度的地圖服務，比如谷歌地圖或百度地圖：
```
function showPosition(position)
{
var latlon=position.coords.latitude+","+position.coords.longitude;

var img_url="http://maps.googleapis.com/maps/api/staticmap?center="
+latlon+"&zoom=14&size=400x300&sensor=false";

document.getElementById("mapholder").innerHTML="<img src='"+img_url+"' />";
}
```
在上例中，我們使用返回的經緯度數據在谷歌地圖中顯示位置（使用靜態圖像）。
谷歌地圖腳本

###getCurrentPosition() 方法 - 返回數據
若成功，則 getCurrentPosition() 方法返回對象。始終會返回 latitude、longitude 以及 accuracy 屬性。如果可用，則會返回其他下面的屬性。

coords.latitude	：十進制數的緯度
coords.longitude：	十進制數的經度
coords.accuracy：	位置精度
coords.altitude：	海拔，海平面以上以米計
coords.altitudeAccuracy：	位置的海拔精度
coords.heading：	方向，從正北開始以度計
coords.speed：	速度，以米/每秒計
timestamp：	響應的日期/時間

###Geolocation 對象 - 其他有趣的方法
watchPosition() - 返回用戶的當前位置，並繼續返回用戶移動時的更新位置（就像汽車上的 GPS）。
clearWatch() - 停止 watchPosition() 方法
下面的例子展示 watchPosition() 方法。您需要一台精確的 GPS 設備來測試該例（比如 iPhone）：
```html
<script>
var x=document.getElementById("demo");
function getLocation()
  {
  if (navigator.geolocation)
    {
    navigator.geolocation.watchPosition(showPosition);
    }
  else{x.innerHTML="Geolocation is not supported by this browser.";}
  }
function showPosition(position)
  {
  x.innerHTML="Latitude: " + position.coords.latitude +
  "<br />Longitude: " + position.coords.longitude;
  }
</script>
```

##HTML5 拖放

###拖放
拖放（Drag 和 Drop）是很常見的特性。它指的是您抓取某物並拖入不同的位置。
拖放是 HTML5 標準的組成部分：任何元素都是可拖放的。

####HTML 拖放實例
下列是關於拖放的簡單例子：
```html
<!DOCTYPE HTML>
<html>
<head>
<script>
function allowDrop(ev) {
    ev.preventDefault();
}

function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}

function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}
</script>
</head>
<body>

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>

<img id="drag1" src="img_logo.gif" draggable="true" ondragstart="drag(event)" width="336" height="69">

</body>
</html>
```
    
###把元素設置為可拖放
首先：為了把一個元素設置為可拖放，請把 draggable 屬性設置為 true：
`<img draggable="true">`
拖放的內容 - ondragstart 和 setData()
然後，規定當元素被拖動時發生的事情。
在上面的例子中，ondragstart 屬性調用了一個 drag(event) 函數，規定拖動什麼數據。
dataTransfer.setData() 方法設置被拖動數據的數據類型和值：
```
function drag(ev) {
    ev.dataTransfer.setData("text", ev.target.id);
}
```
在本例中，數據類型是 "text"，而值是這個可拖動元素的 id ("drag1")。
####拖到何處 - ondragover
ondragover 事件規定被拖動的數據能夠被放置到何處。
默認地，數據/元素無法被放置到其他元素中。為了實現拖放，我們必須阻止元素的這種默認的處理方式。
這個任務由 ondragover 事件的 event.preventDefault() 方法完成：
event.preventDefault()
####進行放置 - ondrop
當放開被拖數據時，會發生 drop 事件。
在上面的例子中，ondrop 屬性調用了一個函數，drop(event)：
```
function drop(ev) {
    ev.preventDefault();
    var data = ev.dataTransfer.getData("text");
    ev.target.appendChild(document.getElementById(data));
}
```
代碼解釋：
調用 preventDefault() 來阻止數據的瀏覽器默認處理方式（drop 事件的默認行為是以鏈接形式打開）
通過 dataTransfer.getData() 方法獲得被拖的數據。該方法將返回在 setData() 方法中設置為相同類型的任何數據
被拖數據是被拖元素的 id ("drag1")
把被拖元素追加到放置元素中

##HTML 本地存儲

HTML 本地存儲：優於 cookies。
###什麼是 HTML 本地存儲？
通過本地存儲（Local Storage），web 應用程序能夠在用戶瀏覽器中對數據進行本地的存儲。
在 HTML5 之前，應用程序數據只能存儲在 cookie 中，包括每個服務器請求。本地存儲則更安全，並且可在不影響網站性能的前提下將大量數據存儲於本地。
與 cookie 不同，存儲限制要大得多（至少5MB），並且信息不會被傳輸到服務器。
本地存儲經由起源地（origin）（經由域和協議）。所有頁面，從起源地，能夠存儲和訪問相同的數據。

###HTML 本地存儲對象
HTML 本地存儲提供了兩個在客戶端存儲數據的對象：
window.localStorage - 存儲沒有截止日期的數據
window.sessionStorage - 針對一個 session 來存儲數據（當關閉瀏覽器標籤頁時數據會丟失）
在使用本地存儲時，請檢測 localStorage 和 sessionStorage 的瀏覽器支持：
```
if (typeof(Storage) !== "undefined") {
    // 針對 localStorage/sessionStorage 的代碼
} else {
    // 抱歉！不支持 Web Storage ..
}
    ```
###localStorage 對象
localStorage 對象存儲的是沒有截止日期的數據。當瀏覽器被關閉時數據不會被刪除，在下一天、周或年中，都是可用的。
```
// 存儲
localStorage.setItem("lastname", "Gates");
// 取回
document.getElementById("result").innerHTML = localStorage.getItem("lastname");
```
實例解釋：
創建 localStorage 名稱/值對，其中：name="lastname"，value="Gates"
取回 "lastname" 的值，並把它插到 id="result" 的元素中
上例也可這樣寫：
```
// 存儲
localStorage.lastname = "Gates";
// 取回
document.getElementById("result").innerHTML = localStorage.lastname;
刪除 "lastname" localStorage 項目的語法如下：
localStorage.removeItem("lastname");
```
注釋：名稱/值對始終存儲為字符串。如果需要請記得把它們轉換為其他格式！
下面的例子對用戶點擊按鈕的次數進行計數。在代碼中，值字符串被轉換為數值，依次對計數進行遞增：
```
if (localStorage.clickcount) {
    localStorage.clickcount = Number(localStorage.clickcount) + 1;
} else {
    localStorage.clickcount = 1;
}
document.getElementById("result").innerHTML = "您已經點擊這個按鈕 " +
localStorage.clickcount + " 次。";
```
###sessionStorage 對象
sessionStorage 對象等同 localStorage 對象，不同之處在於只對一個 session 存儲數據。如果用戶關閉具體的瀏覽器標籤頁，數據也會被刪除。
下例在當前 session 中對用戶點擊按鈕進行計數：
```
if (sessionStorage.clickcount) {
    sessionStorage.clickcount = Number(sessionStorage.clickcount) + 1;
} else {
    sessionStorage.clickcount = 1;
}
document.getElementById("result").innerHTML = "在本 session 中，您已經點擊這個按鈕 " +
sessionStorage.clickcount + " 次。";
```

##HTML5 應用程序緩存

使用應用程序緩存，通過創建 cache manifest 文件，可輕鬆創建 web 應用的離線版本。
###什麼是應用程序緩存？
HTML5 引入了應用程序緩存（Application Cache），這意味著可對 web 應用進行緩存，並可在沒有因特網連接時進行訪問。
應用程序緩存為應用帶來三個優勢：
<b>離線瀏覽 - 用戶可在應用離線時使用它們</b>
<b>速度 - 已緩存資源加載得更快</b>
<b>減少服務器負載 - 瀏覽器將只從服務器下載更新過或更改過的資源</b>


###Cache Manifest 基礎
如需啓用應用程序緩存，請在文檔的 <html> 標籤中包含 manifest 屬性：
```html
<!DOCTYPE HTML>
<html manifest="demo.appcache">
...
</html>
```
每個指定了 manifest 的頁面在用戶對其訪問時都會被緩存。如果未指定 manifest 屬性，則頁面不會被緩存（除非在 manifest 文件中直接指定了該頁面）。
manifest 文件的建議文件擴展名是：".appcache"。
注意：manifest 文件需要設置正確的 MIME-type，即 "text/cache-manifest"。必須在 web 服務器上進行配置。
####Manifest 文件
manifest 文件是簡單的文本文件，它告知瀏覽器被緩存的內容（以及不緩存的內容）。
manifest 文件有三個部分：
<b>CACHE MANIFEST - 在此標題下列出的文件將在首次下載後進行緩存</b>
<b>NETWORK - 在此標題下列出的文件需要與服務器的連接，且不會被緩存</b>
<b>FALLBACK - 在此標題下列出的文件規定當頁面無法訪問時的回退頁面（比如 404 頁面）</b>
####CACHE MANIFEST
第一行，CACHE MANIFEST，是必需的：
```
#####CACHE MANIFEST
/theme.css
/logo.gif
/main.js
```
上面的 manifest 文件列出了三個資源：一個 CSS 文件，一個 GIF 圖像，以及一個 JavaScript 文件。當 manifest 文件被加載後，瀏覽器會從網站的根目錄下載這三個文件。然後，無論用戶何時與因特網斷開連接，這些資源依然可用。
#####NETWORK
下面的 NETWORK 部分規定文件 "login.php" 永遠不會被緩存，且離線時是不可用的：
```
NETWORK:
login.asp
```
可以使用星號來指示所有其他其他資源/文件都需要因特網連接：
```
NETWORK:
*
```

#####FALLBACK
下面的 FALLBACK 部分規定如果無法建立因特網連接，則用 "offline.html" 替代 /html/ 目錄中的所有文件：
```
FALLBACK:
/html/ /offline.html
```
注釋：第一個 URI 是資源，第二個是替補。
###更新緩存
一旦應用被緩存，它就會保持緩存直到發生下列情況：
<b>用戶清空瀏覽器緩存</b>
<b>manifest 文件被修改（參閱下面的提示）</b>
<b>由程序來更新應用緩存</b>
####實例 - 完整的 Cache Manifest 文件
```
CACHE MANIFEST
# 2012-02-21 v1.0.0
/theme.css
/logo.gif
/main.js

NETWORK:
login.asp

FALLBACK:
/html/ /offline.html
```
提示：以 "#" 開頭的是注釋行，但也可滿足其他用途。應用的緩存只會在其 manifest 文件改變時被更新。如果您編輯了一幅圖像，或者修改了一個 JavaScript 函數，這些改變都不會被重新緩存。更新注釋行中的日期和版本號是一種使瀏覽器重新緩存文件的辦法。
###關於應用程序緩存的注意事項
請留心緩存的內容。
一旦文件被緩存，則瀏覽器會繼續展示已緩存的版本，即使您修改了服務器上的文件。為了確保瀏覽器更新緩存，您需要更新 manifest 文件。
注釋：瀏覽器對緩存數據的容量限制可能不太一樣（某些瀏覽器的限制是每個站點 5MB）。

##HTML Web Workers

Web worker 是運行在後台的 JavaScript，不會影響頁面的性能。
###什麼是 Web Worker？
當在 HTML 頁面中執行腳本時，頁面是不可響應的，直到腳本已完成。
Web worker 是運行在後台的 JavaScript，獨立於其他腳本，不會影響頁面的性能。您可以繼續做任何願意做的事情：點擊、選取內容等等，而此時 web worker 運行在後台。

###檢測 Web Worker 支持
在創建 web worker 之前，請檢測用戶瀏覽器是否支持它：
```
if (typeof(Worker) !== "undefined") {
    // 是的！支持 Web worker！
    // 一些代碼.....
} else {
    // 抱歉！不支持 Web Worker！
}
```
###創建 Web Worker 文件
現在，讓我們在一個外部 JavaScript 文件中創建我們的 web worker。
在此處，我們創建了計數腳本。該腳本存儲於 "demo_workers.js" 文件中：
```
var i = 0;

function timedCount() {
    i = i + 1;
    postMessage(i);
    setTimeout("timedCount()",500);
}

timedCount();
```
以上代碼中重要的部分是 postMessage() 方法 - 它用於向 HTML 頁面傳回一段消息。
注釋: web worker 通常不用於如此簡單的腳本，而是用於更耗費 CPU 資源的任務。
###創建 Web Worker 對象
現在我們已經有了 web worker 文件，我們需要從 HTML 頁面調用它。
下面的代碼行檢測是否存在 worker，如果不存在，- 它會創建一個新的 web worker 對象，然後運行 "demo_workers.js" 中的代碼：
```
    if (typeof(w) == "undefined") {
    w = new Worker("demo_workers.js");
}
```
然後我們就可以從 web worker 發生和接收消息了。
向 web worker 添加一個 "onmessage" 事件監聽器：
```
w.onmessage = function(event){
    document.getElementById("result").innerHTML = event.data;
};
```
當 web worker 傳送消息時，會執行事件監聽器中的代碼。來自 web worker 的數據會存儲於 event.data 中。
###終止 Web Worker
當創建 web worker 後，它會繼續監聽消息（即使在外部腳本完成後）直到其被終止為止。
如需終止 web worker，並釋放瀏覽器/計算機資源，請使用 terminate() 方法：
`w.terminate();`
###復用 Web Worker
如果您把 worker 變量設置為 undefined，在其被終止後，可以重復使用該代碼：
w = undefined;
完整的 Web Worker 實例代碼
我們已經看到了 .js 文件中的 Worker 代碼。下面是 HTML 頁面的代碼：
```html
<!DOCTYPE html>
<html>
<body>

<p>Count numbers: <output id="result"></output></p>
<button onclick="startWorker()">Start Worker</button> 
<button onclick="stopWorker()">Stop Worker</button>
<br><br>

<script>
var w;

function startWorker() {
    if(typeof(Worker) !== "undefined") {
        if(typeof(w) == "undefined") {
            w = new Worker("demo_workers.js");
        }
        w.onmessage = function(event) {
            document.getElementById("result").innerHTML = event.data;
        };
    } else {
        document.getElementById("result").innerHTML = "Sorry! No Web Worker support.";
    }
}

function stopWorker() { 
    w.terminate();
    w = undefined;
}
</script>

</body>
</html>
```
###Web Worker 和 DOM
由於 web worker 位於外部文件中，它們無法訪問下例 JavaScript 對象：
<b>window 對象</b>
<b>document 對象</b>
<b>parent 對象</b>
    
    
##HTML Server-Sent 事件

Server-Sent 事件允許網頁從服務器獲得更新。
###Server-Sent 事件 - One Way Messaging
Server-Sent 事件指的是網頁自動從服務器獲得更新。
以前也可能做到這一點，前提是網頁不得不詢問是否有可用的更新。通過 Server-Sent 事件，更新能夠自動到達。
例如：Facebook/Twitter 更新、股價更新、新的博文、賽事結果，等等。

###接收 Server-Sent 事件通知
EventSource 對象用於接收服務器發送事件通知：
```
var source = new EventSource("demo_sse.php");
source.onmessage = function(event) {
    document.getElementById("result").innerHTML += event.data + "<br>";
};
```

例子解釋：
<ul>
<li>創建一個新的 EventSource 對象，然後規定發送更新的頁面的 URL（本例中是 "demo_sse.php"）</li>
<li>每當接收到一次更新，就會發生 onmessage 事件</li>
<li>當 onmessage 事件發生時，把已接收的數據推入 id 為 "result" 的元素中</li>
###檢測 Server-Sent 事件支持
在 TIY 實例中，我們編寫了一段額外的代碼來檢測服務器發送事件的瀏覽器支持：
```
if(typeof(EventSource) !== "undefined") {
    // 是的！支持服務器發送事件！
    // 一些代碼.....
} else {
    // 抱歉！不支持服務器發送事件！
}
```
###服務器端代碼實例
為了使上例運行，您需要能夠發送數據更新的服務器（比如 PHP 或 ASP）。
服務器端事件流的語法非常簡單。請把 "Content-Type" 報頭設置為 "text/event-stream"。現在，您可以開始發送事件流了。
PHP 中的代碼 (demo_sse.php)：
```
<?php
header('Content-Type: text/event-stream');
header('Cache-Control: no-cache');

$time = date('r');
echo "data: The server time is: {$time}\n\n";
flush();
?>
```
ASP 中的代碼 (VB) (demo_sse.asp)：
```
<%
Response.ContentType = "text/event-stream"
Response.Expires = -1
Response.Write("data: The server time is: " & now())
Response.Flush()
%>
```
代碼解釋：
<ul>
<li>把報頭 "Content-Type" 設置為 "text/event-stream"</li>
<li>規定不對頁面進行緩存</li>
<li>輸出要發送的日期（始終以 "data: " 開頭）</li>
<li>向網頁刷新輸出數據</li>

###EventSource 對象
在上例中，我們使用 onmessage 事件來獲取消息。不過還可以使用其他事件：

onopen：	當通往服務器的連接被打開
onmessage：	當接收到消息
onerror：	當發生錯誤