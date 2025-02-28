_開始之前：大部分操作畫面在選單當中連結到裝置上的說明系統，能夠給予相關操作的資訊，你也能輕易找到這段文字。如果你有畫面較大的裝置，例如平板的話，你也能有分割畫面模式來開啟說明文件。所有的說明文件以及其他文件 (常見問題、教學) 也能在  [Vespucci 文件網站](https://vespucci.io/) 找得到。你可以直接在支援快捷方式的裝置直接對著 app 圖示長按，然後選擇"說明"_

# Vespucci 介紹

Vespucci 是全功能的開放街圖編輯器，支援大部分能在桌面版編輯器能做的操作。Vespucci 已經在 Google Android 2.3 到 14.0 ( 4.1 之前的版本已經不支援了) 等多個以 AOSP 為基礎的版本測試成功。忠告：儘管行動裝置的效能已經追上桌機，但在較老的裝置上面，記憶體並不夠，因此運作速度上會很慢。你應該記住上述的事情，並且可能的話，控制自己編輯的區域大小在合理的大小。

## 使用 Vespucci 編輯

根據畫面尺寸和您裝置的新舊，編輯操作可以經由在頂端列的圖示可直接進入，通過下拉選單中頂端列的右側，從底部列(如果存在的話) ，或者透過選單鍵。

<a id="download"></a>

### 下載 OSM 資料

選擇轉移圖示 ![Transfer](../images/menu_transfer.png)，或是轉移選項的項目，這樣會顯示十一個選項：

* **上傳資料到 OSM 伺服器…** - 在 OpenStreetMap 檢視與上傳變動 *(需要認證)* *(需要網路連線)*
* **檢視變動...** - 檢視目前變動
* **下載現有的檢視** - 下載在螢幕上可見的區域，並與所有目前的資料合併*(需要網路連線或是離線資料來源)* 
* **清除現有資料並下載現有的檢視** 清除所有在記憶體中的資料，之後下載在螢幕上可見的區域*(需要網路連線)* 
* **檢索 Overpass...* - 運用 Overpass API 伺服器查詢檢索 *(要網路連線)*
* **依據位置自動下載** - 自動的下載目前周圍位置區域 *(需要網路連線或離線資料)*  *(需要 GPS)*
* **拖放和縮放並自動下載** - 自動下載目前地圖現有的檢視 *(需要網路連線或離線資料)  *(需要 GPS)*
* **更新資料** - 再次從所有區域下載資料，並且更新記憶體當中的資料 *(需要網路連線)*
* **清除資料** - 移除記憶體當中所有 OSM 資料，包括駐列的變動
* **檔案...** - 儲存和載入在裝置的 OSM 檔案資料。
* **任務** -從 QA 工具 (目前的 OSMOSE) 下載 (自動或手動) OSM 備註和"錯誤" *(需要網路連線)*

最簡單下載資料到裝置的方式是縮放和平移到你想編輯的地方，接著選擇 "下載當前檢視"。你可以用手勢縮放，用縮放按鈕，或是用裝置的音量鍵。Vespucci 應當下載當前檢視的資料，下載資料到裝置時並不需要認證。

採用非鎖定設定時，所有非下載區域相比下載區域會用暗淡色顯示，只有在放大到一定程度才會允許編輯。這是要避免在未顯示區域不適當的新增重覆物件。在鎖定狀態時，暗淡色顯示則會取消，而在[進階設定](Advanced%20preferences.md)當中能改變行為，能夠一直以暗淡色顯示。

如果你需要非正規 OSM API 輸入，或是以 _MapSplit_ 格式使用[離線資料](https://vespucci.io/tutorials/offline/)，你可以在 _設定..._ 的圖層控制當中資料圖層那邊改變。

### 編輯

<a id="lock"></a>

### 鎖定，解鎖，模式切換

要避免不小心編輯的狀況，Vespucci 啟動時處於"鎖定"模式。處於鎖定模式時只允許縮放和移動地圖。點 ![Locked](../images/locked.png)  圖示則會解鎖螢幕。 

在鎖定圖示長按，或是在地圖顯示的  _模式_ 選單，跳出選單會顯示以下四個選項：

* **正常** - 預設的編輯模式，新物件能被添加，既有的物件可以被編輯、移動和移除。用簡單的白色鎖定圖示表示。
* **只有標籤** - 選擇既有的物件會跳進內容編輯器，由綠色 "+" 按鈕或是長按新增物件，但不會有任何幾何動作。用白色鎖定圖示加上"T"的方式表示。
* **地址** - 啟動地址模式，有一些特別功能加上稍微簡化過的[簡單模式](../en/Simple%20actions.md) "+" 用白色鎖定圖示加上"A"的方式表示。
* **室內** - 啟動室內模式，請見[室內模式](#indoor)。用白色鎖定圖示加上"I"的方式表示。
* C-模式** - 啟動 C-模式，只有上面有警告標示的物件會顯示，請見 [C-模式](#c-mode)。用白色鎖定圖示加上"C"的方式表示。

如果你使用 Vespucci 的 Android 裝置支援快捷選項 (對著 app 圖示長按)，你可以直接進入 _地址_ 與 _室內_ 模式。

#### 單點，雙點和長按

根據預設設定，可選擇的節點或是路徑周圍會出現橘色區域，粗略表示你可以從那裡選碰觸選擇物件。你有三個選擇：

* 單點：選取物件。
  * 孤單的節點/路徑馬上會高亮度顯示。
  * 然後，如果你選取物件，但 Vespucci 覺得選取方式可能意味要多重選擇的話，會顯示選取選單，讓你能決定選那個物件。
  * 選取的物件會以黃色高亮度顯示。
  * 要看更多資訊，請看[節點選擇](Node%20selected.md)， [路徑選擇](Way%20selected.md)和[關係選擇](../en/Relation%20selected.md)
* 雙點：開啟[多重選擇模式](Multiselect.md) 
* 長按：新建"十字準線"，讓你能新增節點，請見下面敘述和[新建新物件](Creating%20new%20objects.md)。這只有在"簡單模式"未啟用才能用。

如果您試著編輯高密度區域時進行放大，這是一個很好的對策。

Vespucci 擁有一個良好的"取消/重做"系統，所以不要害怕在您的裝置嘗試，但是請不要上傳和儲存純測試資料。

#### 選擇/取消選擇 (單擊和“選擇選單”)

碰觸物件選取和高亮度顯示物件，碰觸螢幕空白處則會取消選取。如果你選取物件後你想再選取其他物件，就輕觸你想選取的物件，不需要先解除選取。在物件雙點會啟用[多重選取模式](Multiselect.md)。

注意如果你嘗試選取物件，而 Vespucci 覺得這次選取重作可能意味多重選取物件 (像是路徑上的節點，或是重疊的物件)，之後會出現選取選單：點你想選取的物件，物件就會被選取。 

選取物件會以黃色細邊線顯示，黃色邊線也許會難以查察，視地圖背景和放大因子而定。一旦選取，你會看到通知確認要選取。

一旦選取完成，你會看到 (可能是按鈕或是選單項目) 對選取物件的支援操作清單。要看更多資訊，請見 [物件選取](Node%20selected.md), [路徑選取](Way%20selected.md)和[關係選取](Relation%20selected.md)。

#### 選擇物件：編輯標籤

第二次碰觸選取物件會開啟標籤編輯器，而你可以編輯選取物件的標籤。

注意當有重疊的物件 (像是路徑上的節點)，選取選單會再次顯示。選取相同物件則會出現標籤編輯器，選取其他物件則會轉而選取其他物件。

#### 選擇物件：移動節點或路徑

一旦你選取物件，也可以移動。注意這個物件在選取動況可以被拖動/移動。簡單在選取物件附近拖動 (在容忍範圍內)。如果你在[設定](Preferences.md)中選擇大拖動範圍，你在選擇節點時會有物件附近的大範圍，能讓你有很方便置放物件。 

#### 增加新節點/點或是路徑 

啟動 App 時就啟用"簡單模式"，這個設定能透過取消選取相對應的核取方塊，在主要選單中更動。

##### 簡易模式

按著地圖畫面上的綠色浮動按鈕，能顯示選單。當你選擇其中一個項目時，你會被問到想在那個位置新建物件，持續平移和縮放到你想要的地圖畫面為止。 

請看[簡單模式下新增物件](Simple%20actions.md) 來得到更多資訊。簡單模式為新安裝的預設值。

##### 進階 (長按) 模式

在你創建節點或是路徑開始的地方長按，你會看到黑色"十字"圖樣。
* 如果你想要創建新的節點 (並沒有連到其他物件)，請避開按到其他已有的物件。
* 如果你想延伸路徑，按在路徑的"容許區域" (或是路徑上的節點)內。容許區域會顯示在節點或是路徑周邊。

一旦你看到準星圖示，你有這些選擇：

* _正常按同一地方。_
  * 如果十字準星不在節點附近，碰觸同一地方則會再次創建新的節點。如果附近有路徑 (但不在節點附近)，新的節點會在路徑上面 (並且連到路徑上面)。
  * 如果十字準星靠近節點瓶近 (例如在節點容忍範圍)，碰觸相同地方只會選取節點 (標籤編輯器會出現，不會有創建新的節點)。操作的過程與上述敘述一樣。
* _正常碰觸其他地方。_碰觸其他地點 (在十字準星容忍範圍外) 則會從原始地點到現在位置新增路徑。如果十字準星在路徑或節點附近，新的片段會連到該節點或是路徑。　

簡單在你想增加節點的路徑上碰觸螢幕，要完成操作，請在最後一個節點碰觸兩次。如果最後的節點位於路徑或是節點，則片段會自動連到路徑或是節點。 

你也可以使用選單項目：請見[創建新物件](Creating%20new%20objects.md) 來獲得更多資訊。

#### 增加區域

目前開放街圖並沒有如其他地理資訊系統一樣，有"區域"物件類型。線上編輯器 "iD" 編輯嘗試在現有 OSM 架構下，建立區域類型，目前看來在特定狀況下運作相當好，也有不能好好運作的時候。Vespucci 目前並沒有計畫像 iD 一樣做類似的事情，所以你必須知道路徑區域是怎麼構成的：

* _封閉路徑 ("多邊形*)_：最簡單與最常見的區域類型，共享第一個節點與最後個節點的路徑來形成封閉的"環形" (例如說大部分的建築都是屬於這類)。封閉路徑相當容易在 Vespucci 新建，只要畫區域時連回第一個節點就可以了。注意：如何解讀封閉路徑端看加上去的標籤：例如說，如果封閉路徑標為建築，則會視為區域，如果標為圓環則不會。在一些情境當中，兩種解讀則都有效，加上 "area" 標籤能夠清楚區別用途。
* _多重多邊形_：有些區域有多個部分，穿洞與環形，無法只有一個路徑表示。OSM 採用特定型態的關聯 (我們一般用途物件能用關聯模型來連結) 來處理上述狀況，也就是多重多邊形。多重多邊形有"外圍"環形與"內部"環形。每個環形可以是上述提及的封閉路徑，或是多個分享結束節點的獨立路徑。當大型多重多邊形很難被任何工具處理，但小型的多邊形能輕易用 Vespucci 來處理。
* _海岸線_：對於相當大的物件、大陸與島嶼，即便是多重多邊形也無法圓滿來處理。對於 natural=coastline 路徑我們假設是方向相關的片段：陸地是在路徑的左側，而水域則在路徑的右側。然而這樣定義有個副作用，一般來說，你不應該反轉有海岸線標籤的路徑方向。你可以在  [OSM wiki](http://wiki.openstreetmap.org/wiki/Tag:natural%3Dcoastline) 閱讀更多資訊。

#### 改善道路的幾何形狀

如果你放大到夠大的程度，選取夠長的路徑中間會看到小的"x"。拖動"x"會在路徑位置上創建新的節點。注意：要避免不小心創新節點，因此操作碰觸的容忍區域相當小。

#### 剪下、複製和貼上

您可以複製選擇的節點和路徑，然後貼上一次或多次到一個新的位置。剪切將保留 OSM ID 和版本，但只能貼上一次。要貼上長按要貼上的位置(您會看到一個十字線標記的位置)。然後從選單中選擇“貼上”。

#### 有效的增加地址

Vespucci 支援能更有效率在現地調查地址的功能，那就是預測門牌號碼功能 (分別在道路左側與右側作用)，以及依據位置與上次使用的值自動添加 _addr:street_ 或者 _addr:place_。在最佳情境下，能夠允許添加地址時不用輸入任何資訊。   

可以長按 ![Address](../images/address.png) 來啟動新增標籤： 

* 長按之後 (只有在非簡單模式下)：Vespucci 會在該位置新增節點，然後依據最近狀況猜測這邊的門牌號碼與地址標籤。如果節點在建築外緣則會自動在該節點加上 "entrance=yes" 標籤。標籤編輯器將會對有疑問的物件開啟，然後可以做進一步的編輯。
* 在節點/路徑選取模式：Vespucci 會像上述那樣添加地址標籤，然後啟動標籤編輯器。
* 在屬性編輯器。

要直接新增單獨的地址節點的話，則是在預設的"簡單模式"切換到"地址"編輯模式(長按鎖按鈕)，"新增地址節點"則會在該位置新增地址節點，而如果在建築外緣則會像前述那樣加出入口標籤。

門牌號碼預測，一般需求要在道路的兩側，至少兩間房屋號碼需要輸入到作業中，更多的號碼存在於資料中越好。

考慮用這個功能搭配[自動下載](#download)模式。  

#### 增加轉​​彎限制

Vespucci 有個快速增加轉彎限制的功能。如果需要則可以自動切割路徑，並且詢問後重新選擇物件。 

* 選取有道路標籤的路徑(轉彎限制只能加道路。如果你需要用其他方式做的話，請使用一般的"創建關係"模式)
* 從選單選取"增加限制"
* 選取"經由"節點或路徑 (只有"經由"元件有觸控區域顯示才有可能)
* 選取"到"路徑 (雙重後退和設定"到"元件變成"從"元件才有可能，Vespucci 會假設你增加不可迴轉限制)
* 設定限制種類

### Vespucci"鎖定"模式

當紅色鎖定圖示顯示時，所有非編輯動作都可以做。除此之外，長按或是接近物件時，如果是OSM物件時會顯示詳細資訊視窗

### 儲存您的變更

*(需要網路連線)*

選擇您在下載時相同的按鈕或選單項目，現在選擇 "上傳資料到 OSM 的伺服器"。

Vespucci 支援 OAuth 2，OAuth 1.0a 認證機制以及傳統的帳號名稱與密碼方式。自從 2024 年 7 月 1 日開始 OpenStreetMap API 只支援 OAuth 2，而其他方式則只在私有站點的 API 或是其他使用 OSM 軟體的計畫。  

認證 Vespucci 連結你帳號，需要你以你帳號與密碼先登入一次。如果你的 Vespucci 還未認證，會在上傳變動的資料時，要求你到 OSM 網站登入 (透過加密連線)。當你登入後，會要求你授權 Vespucci 以你帳號編輯。如果你想要在編輯前授權 OAuth 連接你帳號，請到選單中的"工具" 當中設定好。

如果您想要儲存您的工作，並且不能連入網際網路，您可以儲存成 JOSM 相容的 .osm 檔案，以後以 Vespucci 或 JOSM 任何一個上載。 

#### 在上傳解決衝突

Vespucci 有個簡單的衝突解決。不管怎樣，如果您于您的編輯察覺到有重要事件，將您的更改匯出到 .osc  檔案 (在"傳輸"選單中"匯出"的選單項目) 並且修復和上傳給 JOSM。請參閱有關詳細的説明 [衝突解決](Conflict%20resolution.md)。  

### 顯示附近興趣點

顯示附近興趣點可以在底部選單中間拉起選項。 

更多主選單上這個或其他可用的選項能在這邊[顯示主要地圖](Main%20map%display.md)找到。

## 使用 GPS 與 GPX 軌跡

當在標準設定時，Vespucci 會嘗試打開 GPS (以及其他依據衛星定位的導航系統)，如果不行才會退下來用"電信網路"來定位。這項行為預設你是在正常狀態使用你的 Android 裝置，只採用 GPX 產生的位置 (避免遭到追蹤)，就是委婉寫做"改進定位準確度"選項關閉。如果你想啟用這選項，但想避免 Vespucci 退下來採用"電信網路位置"，你應該在 [進階設定](Advanced%20preferences.md)關閉該選項。 

碰觸 ![GPS](../images/menu_gps.png)按鈕 (通常在地圖顯示的左側) 則會以目前位置置中螢幕，而當你移動地圖顯示時，則會維持置中。手動移動螢幕或是編輯時則會關閉"跟隨GPS"模式，以及藍色GPS箭頭則從輪廓變實心箭頭。要快速回到"跟隨"模式，只要碰觸 GPS 按鈕或是按其他選單選項。如果裝置沒有目前位置的標記/箭頭則會顯示為黑色，如果有目前位置則會顯示為藍色。

要錄製 GPS 軌跡並且在裝置上顯示，你要在![GPS](../images/menu_gps.png) 選單選擇"開始錄製GPX軌跡"。這會在螢幕上新增目前錄製軌跡圖層，你可以在 [圖層控制](Main%20map%20display.md)上傳或是匯出軌跡。你可以新增本地 GPX 檔案與從 OSM API 下載軌跡變成其他圖層。

注意：預設 Vespucci 不會在錄製 GPX 軌跡時記錄高度，這是因為一些 Android 裝置的特殊問題。要啟用高度記錄，需要啟用高度記錄，或是安裝重力模組，或是更簡單到[進階設定](Advanced%20preferences.md) 設定 NMEA 輸入。

### 如何匯出 GPS 軌跡？

開啟圖層選單，接著點在"GPS錄製"旁邊的3點選單，最後選擇**輸出GPX軌跡...**。選擇那個資料夾來匯出，接著以`.gpx`的後綴命名檔案 (例如：MyTrack.gpx)。

## 備註、錯誤和待辦事項

Vespucci 支援下載、回應和關閉 OSM 註解 (先前的 OSM 臭蟲)，以及相等功能由 [OSMOSE 品質監控工具](http://osmose.openstreetmap.fr/en/map/)產生的"臭蟲"。兩者都能完整下載下來，或者你可以使用自動下載功能，馬下輔助你取得所在區域的物件。一旦編輯或關閉，你可以馬上上傳臭蟲或是註解，或是全部一次上傳。 

接著我們支援能從 OSM 元素，從 GeoJSON 圖層，或是從 Vespucci 外部新增的"待辦事項"，這能夠提供方便追蹤你想要完成的事項的方式。 

註解和臭蟲會以小蟲子圖示  ![Bug](../images/bug_open.png) 顯示在地圖上面，綠色代表關閉/解決，藍色代表被新增或是由你編輯過，而黃色表示仍然有效還沒有變動。待辦事項則會以黃色勾選框顯示。

OSMOSE 錯誤以及待辦事項的顯示會將受影響的元素有連結，以藍色呈現出來 (而待辦事頁則只會顯示相關的 OSM 元素)，碰觸連結則會選擇元素，置中螢幕並且必要時先下載區域的資料。 

### 篩選

除了全域時啟用顯示註解和臭蟲以外，你可以設定粗略顯示過瀘降低雜亂程度。你可以從任務圖層當中的[圖層控制](#layers)當中，設定過濾選項：

* 註解
* Osmose 錯誤
* Osmose 警告
* Osmose 小問題
* Maproulette
* 待辦事項

<a id="indoor"></a>

## 室內模式

室內繪圖由於有相當多的物件而且常常彼此重疊，因此是相當有挑戰性的事情。Vespucci 發展出室內模式，能夠允許你過濾其他不在同一層的所有物件，並且自動加上目前樓層資訊到新增加的物件上面。

這個模式可以透過長按鎖定鈕，請見[鎖定、解鎖、切換模式](#lock)，然後選擇對應的選單選項。

<a id="c-mode"></a>

## C-模式

在 C-模式下，只有擁有警告標示的物件才會顯示，讓檢視有特定問題或符合設定檢查的物件變得更容易。C-模式下啟動的內容編輯器，最符合的預設組合會自動套用。

這個模式可以透過長按鎖定鈕，請見[鎖定、解鎖、切換模式](#lock)，然後選擇對應的選單選項。

### 設定檢查

所有的驗證都能在[設定](Preferences.md)"驗證設定/啟用驗登"當中被關閉/開啟。 

"重新踏查"的設定允許你設定一段時間重新踏查特定的標籤組合的物件。"檢查"項目則視符合的預置而被呈現出來。你可以點項目來編輯項目，綠色選單按鈕則允許新增項目。

#### 重新踏察選項

重新踏察列表擁有以下內容：

* **鍵** - 感興趣標籤的鍵。
* **值** - 感興趣標籤應該要的值，如果是空白的話則標籤的值會被忽略。
* **年齡** - 離上次元素變動的時間過了多少天了，代表可能需要重新踏察。如果有 _check_date_ 標籤則會用到，不然就是依據現在版本是那一天創建的。設為零則會簡單檢查鍵和值。
* **正規表示式** - 如果檢查 **值**則會假定是 JAVA 的正規表示式。 

**鍵** 和 **值** 會與問題物件 _existing_ tags 相比檢查。

在標準預設組合當中的_Annotations_ 群組中 ，含有物件能夠自動增加現在時間的 _check_date_ 標籤。

#### 檢查選項

檢查列表有兩個內容：

* **鍵** - 鍵應當依據符合的預置出現在相對的物件。
* **需要的選填** - 即便是符合的預置的選填標籤，也會需要鍵。

這次檢查會先決定符合的預置，接著檢查**鍵**是否是預置推薦的"建議"鍵值。**必須的選擇性**則會擴大檢查物件標籤中的"選擇性"標籤。注意：目前連結的預置並不會檢查。

## 篩選

### 標籤為依據的篩選

在主選單能啟用過濾器，可以按過濾器的圖示變更。更多說明文件可以到這邊[標籤過濾器](Tag%20filter.md)。

預置為依據的篩選

上述的替代方式，依據單一預設組合或是預先組合群組過濾物件。按過濾圖示會顯示預設組合選擇選單，類似 Vespucci 裡見到的選單。只要正常按一下就可以選擇單一預設組合，要選擇預設組合群組則長按 (正常按一下之後進入群組)。更多文件說明可到這裡這邊尋找[預設組合過濾器](Preset%20filter.md)。

## 客製化 Vespucci

這款 app 很多方面都能自訂，如果你想要特別的功能但找不到的話，可以到 [Vespucci 網站](https://vespucci.io/)搜尋，尋找裝置上的額外資訊。

<a id="layers"></a>

### 圖層設定

圖層設定可以藉由圖層控制來改變 (在右上角"漢堡"選項)，所有其他設定可以透過主選項設定按鈕設定進入。可以啟動、關闢或暫時隱藏圖層。

可用的圖層種類：

* 資料圖層 - 這是開放街圖資料會載入的圖層，一般來說使用上不必更動。預設：啟用。
* 背景圖層 - 這裡有相當多可供使用的空照和衛星背景影像，預設的數值是 openstreetmap.org 的"標準樣式"地圖。
* 重疊圖層 - 這些是有額外資訊的半透明圖層，像是品質檢查資訊。增加重疊圖層也許會對較老的裝置和有限記憶體裝置造成負擔。預設：無。
* 註解/臭蟲顯示。開啟註解和臭蟲會以黃色蟲子圖示來顯示，關閉的則會顯示綠色。預設：開啟。
* 圖片圖層，會顯示地理參照的圖片為紅色攝影機圖示，如果有方向資訊則會轉向。預設：關閉。
* Mapillary 圖層 - 顯示有影像存在具有標記的 Mapillary 片段，點標記則會顯示影像。預設：關閉。
* GeoJSON 圖層 - 顯示 GeoJSON 檔案的內容，多個圖層可以從檔案新增。預設：關閉。
* GPX 圖層 -顯示 GPX 軌跡與路徑節點，多個圖層可以從檔案新增，而在記錄軌跡時 GPX 軌跡會另外顯示。預設：關閉。
* 網格 - 在地圖兩邊顯示尺規或網格。預設：啟用。 

更多資訊能在[地圖顯示](Main%20map%20display.md)取得。

#### 參數選項 

* 保持螢幕開啟。預設：關閉。
* 巨大節點拖曳區，當裝置觸控輸入導致移動節點有問題時，手指會在顯示目前位置採模糊顯示。開啟這個選項會提供大片區域，來用在非中心的拖拉上 (選擇和其他操作仍會使用正常的觸控容許範圍)。預設：關閉。

整個敘述能在這裡[設定](Preferences.md)找到

進階參數選項

* 全螢幕模式。在沒有硬體按鈕的裝置上，Vespucci 能夠以全螢幕方式運作，這意味著"虛擬"瀏覽按鈕將在地圖顯示時自動被隱藏，提供地圖更多螢幕空間。而視你裝置也許能運作也許不能。在 _自動_ 模式我們會自動偵測，視設定為 _強制_ 或是 _總不_ 來決定是否啟用全螢幕模式，或是跳過自動檢查，而總是啟用全螢幕或是總不使用。而在使用 Android 11 或以上版本，_自動_ 模式因為有 Android 的手勢提供替代操作方式，則不會啟用全螢幕模。預設：_自動_。
* 節點圖示。預設：_啟用_。
* 總是顯示內容選單。當啟用所有選擇程序，則會顯示內容選單，關閉選單有顯示則只會在沒有明顯選擇時來決定。預設：關閉 (先前為啟用)。
* 啟用亮色主題。在現代裝置則是預設開啟。你仍可以為較舊版本 Anroid 啟用，但樣式可能不一致。 

整個敘述能在這裡[進階設定](Advanced%20preferences.md)找到

## 回報與解決問題

如果 Vespucci 當掉，或是偵測不一致的狀態，你會被詢問是否傳送當機報告。如果發生的話請寄送報告，但請一次描述特定狀況。如果你想提供更多資訊，或是開啟 issue 請求新功能或其他類似請求，請到這邊開：[Vespucci issue tracker](https://github.com/MarcusWolschon/osmeditor4android/issues)。主選單的"提供回饋"功能會開放新的 issue，不用額外輸入就有包含相關的 app 和裝置資訊。

如果你遇到困難，開啟 app 後當掉，你可以在支援快捷鍵的裝置當中以 _安全_ 模式開啟：對著 app 圖示長按，然後在選單選擇 _安全_ 模式。 

如果你想討論 Vespucci 相關議題，你可以在[開放街圖討論區](https://community.openstreetmap.org)開啟討論。


