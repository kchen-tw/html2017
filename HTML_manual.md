##HTML 全局属性
| 屬性  | 描述  |
|---|---|
|accesskey	|規定激活元素的快捷鍵。|
|class	|規定元素的一個或多個類名（引用樣式表中的類）。|
|contenteditable	|規定元素內容是否可編輯。|
|contextmenu|	規定元素的上下文菜單。上下文菜單在用戶點擊元素時顯示。|
|data-*	|用於存儲頁面或應用程序的私有定制數據。|
|dir	|規定元素中內容的文本方向。|
|draggable	|規定元素是否可拖動。|
|dropzone|	規定在拖動被拖動數據時是否進行複製、移動或鏈接。|
|hidden	|規定元素仍未或不再相關。|
|id	|規定元素的唯一 id。|
|lang	|規定元素內容的語言。|
|spellcheck|	規定是否對元素進行拼寫和語法檢查。|
|style	|規定元素的行內 CSS 樣式。|
|tabindex|	規定元素的 tab 鍵次序。|
|title	|規定有關元素的額外信息。|
|translate|	規定是否應該翻譯元素內容。|

##全局事件屬性
HTML 4 增加了使事件在瀏覽器中觸發動作的能力，比如當用戶點擊元素時啓動 JavaScript。
如需學習更多有關事件編程的知識，請訪問我們的 JavaScript 教程。
下面列出了添加到 HTML 元素以定義事件動作的全局事件屬性。

###Window 事件屬性
|屬性 | 值 | 描述 |
|---|---|---|
|onafterprint	|script|	文檔打印之後運行的腳本。|
|onbeforeprint|	script	|文檔打印之前運行的腳本。|
|onbeforeunload	|script|	文檔卸載之前運行的腳本。|
|onerror	|script	|在錯誤發生時運行的腳本。|
|onhaschange	|script	|當文檔已改變時運行的腳本。|
|onload	|script	|頁面結束加載之後觸發。|
|onmessage|	script|	在消息被觸發時運行的腳本。|
|onoffline	|script	|當文檔離線時運行的腳本。|
|ononline	|script	|當文檔上線時運行的腳本。|
|onpagehide	|script	|當窗口隱藏時運行的腳本。|
|onpageshow	|script|	當窗口成為可見時運行的腳本。|
|onpopstate|	script	|當窗口歷史記錄改變時運行的腳本。|
|onredo|	script	|當文檔執行撤銷（redo）時運行的腳本。|
|onresize|	script	|當瀏覽器窗口被調整大小時觸發。|
|onstorage	|script	|在 Web Storage 區域更新後運行的腳本。|
|onundo	|script	|在文檔執行 undo 時運行的腳本。|
|onunload|	script	|一旦頁面已下載時觸發（或者瀏覽器窗口已被關閉）。|

###Form 事件
|屬性 | 值 | 描述 |
|---|---|---|
|onblur	|script|	元素失去焦點時運行的腳本。|
|onchange|	script	|在元素值被改變時運行的腳本。|
|oncontextmenu	|script	|當上下文菜單被觸發時運行的腳本。|
|onfocus	|script	|當元素獲得焦點時運行的腳本。|
|onformchange	|script	|在表單改變時運行的腳本。|
|onforminput|	script	|當表單獲得用戶輸入時運行的腳本。|
|oninput|	script	|當元素獲得用戶輸入時運行的腳本。|
|oninvalid|	script	|當元素無效時運行的腳本。|
|onreset|	script	|當表單中的重置按鈕被點擊時觸發。HTML5 中不支持。|
|onselect	|script	|在元素中文本被選中後觸發。|
|onsubmit|	script|	在提交表單時觸發。|

###Keyboard 事件
|屬性 | 值 | 描述 |
|---|---|---|
|onkeydown|	script|	在用戶按下按鍵時觸發。|
|onkeypress|	script	|在用戶敲擊按鈕時觸發。|
|onkeyup|	script|	當用戶釋放按鍵時觸發。|

###Mouse 事件
|屬性 | 值 | 描述 |
|---|---|---|
|onclick|	script|	元素上發生鼠標點擊時觸發。|
|ondblclick|	script	|元素上發生鼠標雙擊時觸發。|
|ondrag	|script|	元素被拖動時運行的腳本。|
|ondragend|	script	|在拖動操作末端運行的腳本。|
|ondragenter	|script	|當元素元素已被拖動到有效拖放區域時運行的腳本。|
|ondragleave	|script	|當元素離開有效拖放目標時運行的腳本。|
|ondragover	|script	|當元素在有效拖放目標上正在被拖動時運行的腳本。|
|ondragstart	|script	|在拖動操作開端運行的腳本。|
|ondrop|	script|	當被拖元素正在被拖放時運行的腳本。|
|onmousedown	|script	|當元素上按下鼠標按鈕時觸發。|
|onmousemove|	script|	當鼠標指針移動到元素上時觸發。|
|onmouseout|	script	|當鼠標指針移出元素時觸發。|
|onmouseover|	script	|當鼠標指針移動到元素上時觸發。|
|onmouseup	|script	|當在元素上釋放鼠標按鈕時觸發。|
|onmousewheel	|script	|當鼠標滾輪正在被滾動時運行的腳本。|
|onscroll|	script	|當元素滾動條被滾動時運行的腳本。|

###Media 事件
|屬性 | 值 | 描述 |
|---|---|---|
|onabort|	script|	在退出時運行的腳本。|
|oncanplay	|script	|當文件就緒可以開始播放時運行的腳本（緩衝已足夠開始時）。|
|oncanplaythrough|	script|	當媒介能夠無需因緩衝而停止即可播放至結尾時運行的腳本。|
|ondurationchange|	script	|當媒介長度改變時運行的腳本。|
|onemptied	|script	|當發生故障並且文件突然不可用時運行的腳本（比如連接意外斷開時）。|
|onended|	script|	當媒介已到達結尾時運行的腳本（可發送類似「感謝觀看」之類的消息）。|
|onerror|	script|	當在文件加載期間發生錯誤時運行的腳本。|
|onloadeddata	|script	|當媒介數據已加載時運行的腳本。|
|onloadedmetadata|	script|	當元數據（比如分辨率和時長）被加載時運行的腳本。|
|onloadstart	|script|	在文件開始加載且未實際加載任何數據前運行的腳本。|
|onpause|	script|	當媒介被用戶或程序暫停時運行的腳本。|
|onplay	|script	|當媒介已就緒可以開始播放時運行的腳本。|
|onplaying|	script|	當媒介已開始播放時運行的腳本。|
|onprogress	|script	|當瀏覽器正在獲取媒介數據時運行的腳本。|
|onratechange|	script|	每當回放速率改變時運行的腳本（比如當用戶切換到慢動作或快進模式）。|
|onreadystatechange|	script|	每當就緒狀態改變時運行的腳本（就緒狀態監測媒介數據的狀態）。|
|onseeked|	script|	當 seeking 屬性設置為 false（指示定位已結束）時運行的腳本。|
|onseeking	|script|	當 seeking 屬性設置為 true（指示定位是活動的）時運行的腳本。|
|onstalled|	script|	在瀏覽器不論何種原因未能取回媒介數據時運行的腳本。|
|onsuspend|	script|	在媒介數據完全加載之前不論何種原因終止取回媒介數據時運行的腳本。|
|ontimeupdate|	script|	當播放位置改變時（比如當用戶快進到媒介中一個不同的位置時）運行的腳本。|
|onvolumechange|	script|	每當音量改變時（包括將音量設置為靜音）時運行的腳本。|
|onwaiting|	script|	當媒介已停止播放但打算繼續播放時（比如當媒介暫停已緩衝更多數據）運行腳本|

##HTML5 視頻和音頻的 DOM 參考手冊
###HTML5 Audio/Video 方法
|方法 | 描述 |
|---|---|
|addTextTrack()|	向音頻/視頻添加新的文本軌道|
|canPlayType()	|檢測瀏覽器是否能播放指定的音頻/視頻類型|
|load()|	重新加載音頻/視頻元素|
|play()	|開始播放音頻/視頻|
|pause()	|暫停當前播放的音頻/視頻|

###HTML5 Audio/Video 屬性
|屬性 | 描述 |
|---|---|
|audioTracks|	返回表示可用音軌的 AudioTrackList 對象|
|autoplay	|設置或返回是否在加載完成後隨即播放音頻/視頻|
|buffered	|返回表示音頻/視頻已緩衝部分的 TimeRanges 對象|
|controller|	返回表示音頻/視頻當前媒體控制器的 MediaController 對象|
|controls	|設置或返回音頻/視頻是否顯示控件（比如播放/暫停等）|
|crossOrigin	|設置或返回音頻/視頻的 CORS 設置|
|currentSrc|	返回當前音頻/視頻的 URL|
|currentTime	|設置或返回音頻/視頻中的當前播放位置（以秒計）|
|defaultMuted|	設置或返回音頻/視頻默認是否靜音|
|defaultPlaybackRate|	設置或返回音頻/視頻的默認播放速度|
|duration	|返回當前音頻/視頻的長度（以秒計）|
|ended|	返回音頻/視頻的播放是否已結束|
|error	|返回表示音頻/視頻錯誤狀態的 MediaError 對象|
|loop|	設置或返回音頻/視頻是否應在結束時重新播放|
|mediaGroup	|設置或返回音頻/視頻所屬的組合（用於連接多個音頻/視頻元素）|
|muted|	設置或返回音頻/視頻是否靜音|
|networkState|	返回音頻/視頻的當前網絡狀態|
|paused|	設置或返回音頻/視頻是否暫停|
|playbackRate|	設置或返回音頻/視頻播放的速度|
|played|	返回表示音頻/視頻已播放部分的 TimeRanges 對象|
|preload	|設置或返回音頻/視頻是否應該在頁面加載後進行加載|
|readyState	|返回音頻/視頻當前的就緒狀態|
|seekable|	返回表示音頻/視頻可尋址部分的 TimeRanges 對象|
|seeking|	返回用戶是否正在音頻/視頻中進行查找|
|src|	設置或返回音頻/視頻元素的當前來源|
|startDate|	返回表示當前時間偏移的 Date 對象|
|textTracks|	返回表示可用文本軌道的 TextTrackList 對象|
|videoTracks|	返回表示可用視頻軌道的 VideoTrackList 對象|
|volume|	設置或返回音頻/視頻的音量|

###HTML5 Audio/Video 事件
|事件 | 描述 |
|---|---|
|abort|	當音頻/視頻的加載已放棄時|
|canplay|	當瀏覽器可以播放音頻/視頻時|
|canplaythrough|	當瀏覽器可在不因緩衝而停頓的情況下進行播放時|
|durationchange|	當音頻/視頻的時長已更改時|
|emptied|	當目前的播放列表為空時|
|ended	|當目前的播放列表已結束時|
|error|	當在音頻/視頻加載期間發生錯誤時|
|loadeddata|	當瀏覽器已加載音頻/視頻的當前幀時|
|loadedmetadata|	當瀏覽器已加載音頻/視頻的元數據時|
|loadstart	|當瀏覽器開始查找音頻/視頻時|
|pause|	當音頻/視頻已暫停時|
|play|	當音頻/視頻已開始或不再暫停時|
|playing|	當音頻/視頻在已因緩衝而暫停或停止後已就緒時|
|progress|	當瀏覽器正在下載音頻/視頻時|
|ratechange|	當音頻/視頻的播放速度已更改時|
|seeked|	當用戶已移動/跳躍到音頻/視頻中的新位置時|
|seeking	|當用戶開始移動/跳躍到音頻/視頻中的新位置時|
|stalled|	當瀏覽器嘗試獲取媒體數據，但數據不可用時|
|suspend	|當瀏覽器刻意不獲取媒體數據時|
|timeupdate	|當目前的播放位置已更改時|
|volumechange|	當音量已更改時|
|waiting|	當視頻由於需要緩衝下一幀而停止|

##HTML 5 Canvas 參考手冊
###顏色、樣式和陰影
|屬性 | 描述 |
|---|---|
|fillStyle|	設置或返回用於填充繪畫的顏色、漸變或模式|
|strokeStyle|	設置或返回用於筆觸的顏色、漸變或模式|
|shadowColor|	設置或返回用於陰影的顏色|
|shadowBlur	|設置或返回用於陰影的模糊級別|
|shadowOffsetX|	設置或返回陰影距形狀的水平距離|
|shadowOffsetY	|設置或返回陰影距形狀的垂直距離|

|方法 | 描述 |
|---|---|
|createLinearGradient()|	創建線性漸變（用在畫布內容上）|
|createPattern()	|在指定的方向上重復指定的元素|
|createRadialGradient()|	創建放射狀/環形的漸變（用在畫布內容上）|
|addColorStop()|	規定漸變對象中的顏色和停止位置|

###線條樣式
|屬性 | 描述 |
|---|---|
|lineCap|	設置或返回線條的結束端點樣式|
|lineJoin|	設置或返回兩條線相交時，所創建的拐角類型|
|lineWidth|	設置或返回當前的線條寬度|
|miterLimit|	設置或返回最大斜接長度|

###矩形
|方法 | 描述 |
|---|---|
|rect()|	創建矩形|
|fillRect()	|繪制「被填充」的矩形|
|strokeRect()	|繪制矩形（無填充）|
|clearRect()	|在給定的矩形內清除指定的像素|

###路徑
|方法 | 描述 |
|---|---|
|fill()|	填充當前繪圖（路徑）|
|stroke()	|繪制已定義的路徑|
|beginPath()	|起始一條路徑，或重置當前路徑|
|moveTo()	|把路徑移動到畫布中的指定點，不創建線條|
|closePath()	|創建從當前點回到起始點的路徑|
|lineTo()	|添加一個新點，然後在畫布中創建從該點到最後指定點的線條|
|clip()	|從原始畫布剪切任意形狀和尺寸的區域|
|quadraticCurveTo()|	創建二次貝塞爾曲線|
|bezierCurveTo()	|創建三次方貝塞爾曲線|
|arc()	|創建弧/曲線（用於創建圓形或部分圓）|
|arcTo()	|創建兩切線之間的弧/曲線|
|isPointInPath()	|如果指定的點位於當前路徑中，則返回 true，否則返回 false|

###轉換
|方法 | 描述 |
|---|---|
|scale()|	縮放當前繪圖至更大或更小|
|rotate()	|旋轉當前繪圖|
|translate()	|重新映射畫布上的 (0,0) 位置|
|transform()	|替換繪圖的當前轉換矩陣|
|setTransform()	|將當前轉換重置為單位矩陣。然後運行 transform()|

###文本
|屬性 | 描述 |
|---|---|
|font	|設置或返回文本內容的當前字體屬性|
|textAlign|	設置或返回文本內容的當前對齊方式|
|textBaseline	|設置或返回在繪制文本時使用的當前文本基線|

|方法 | 描述 |
|---|---|
|fillText()|	在畫布上繪制「被填充的」文本|
|strokeText()	|在畫布上繪制文本（無填充）|
|measureText()	|返回包含指定文本寬度的對象|

###圖像繪制
|方法 | 描述 |
|---|---|
|drawImage()	|向畫布上繪製圖像、畫布或視頻|

###像素操作
|屬性 | 描述 |
|---|---|
|width	|返回 ImageData 對象的寬度|
|height|	返回 ImageData 對象的高度|
|data	|返回一個對象，其包含指定的 ImageData 對象的圖像數據|

|方法 | 描述 |
|---|---|
|createImageData()|	創建新的、空白的 ImageData 對象|
|getImageData()|	返回 ImageData 對象，該對象為畫布上指定的矩形複製像素數據|
|putImageData()	|把圖像數據（從指定的 ImageData 對象）放回畫布上|

###合成
|屬性 | 描述 |
|---|---|
|globalAlpha|	設置或返回繪圖的當前 alpha 或透明值|
|globalCompositeOperation	|設置或返回新圖像如何繪制到已有的圖像上|

###其他
|方法 | 描述 |
|---|---|
|save()|	保存當前環境的狀態|
|restore()	|返回之前保存過的路徑狀態和屬性|
|createEvent()||	 
|getContext()|	| 
|toDataURL()||















