---
layout: post
title:  "WWDC 發佈的內容，十個重點"
date:   2019-06-04 12:00:00 +0800
background: 'https://i.imgur.com/E0MbVl7.png'
categories: 一次看完大型活動
---
今年的 WWDC 算是非常豐富的活動，從不用說大家敲碗等了一年的「夜晚模式」(Dark Mode) 到貴鬆鬆買不起的 Mac Pro 都發佈了，關於懶人包網路上俯拾皆是我們這邊就不囉唆了，這邊蘋果宅為大家簡單總結十個關於 WWDC 發佈程式的小重點！

在這之前，先列出能夠取得最新版程式的機型：

**iOS 13**

* iPhone XS & XS Max
* iPhone XR
* iPhone X
* iPhone 8 & 8 Plus
* iPhone 7 & 7 Plus
* iPhone 6s & 6s Plus
* iPhone SE
* iPod touch (第七代)

**iPadOS 13**

* 12.9-inch iPad Pro
* 11-inch iPad Pro
* 10.5-inch iPad Pro
* 9.7-inch iPad Pro
* iPad (第五代與第六代)
* iPad mini (第五代)
* iPad mini 4
* iPad Air (第三代)
* iPad Air 2

**macOS Catalina**

* MacBook 2015 年款以後
* MacBook Air 2012 年款以後
* MacBook Pro 2012 年款以後
* iMac 2012 年款以後
* iMac Pro 2017 年款以後（全部）
* Mac mini 2012 年款以後
* Mac Pro 2013 年款以後

## 一、寫稿當下，iOS, iPadOS第一版的 Beta 沒有提供 OTA 更新用的 Profile

以往 Apple 在測試版軟體都會使用 Profile，以此辨認是不是要提供 OTA 的更新給使用者，但是從昨天晚上大家都發現：這次的 iOS 13 Beta 1 至今都還沒有提供這個 Profile。這大概是因為 Apple 想讓非開發者的使用者不要太輕易取得這個更新，而因為我是 Apple Developer，進到 Portal 之後，還是可以經由安裝 Xcode 或是 macOS Catalina 後，再經由 IPSW 的回復安裝檔將 iOS 13 安裝進我備用的 iPhone 7 Plus 進行測試。

經過一個早上的測試跟探索，我大概能理解為什麼 Apple 不希望大部分的使用者這麼早開始使用 iOS 13。其實每年的 WWDC 比起一個釋出活動，比較像是一個接下來一年的發展藍圖。因此雖然第一版的 Beta 會有一些基本、可行的基本雛型，但是還是很多（非常多）UI 的 Bug 跟還沒有辦法運行的功能。事實上 Apple 還在下載頁上特別留下訊息要大家盡量等到下個月的公測版再使用比較好。

![](https://i.imgur.com/M89V7Ut.png)

而昨天也聽說網路上開始出現一些釣魚網站宣稱擁有 iOS 13 的 Profile，大家請特別注意、留意這些來源，因為目前並沒有從 Apple 釋出的 Profile，這些網站可能是試圖想要植入一些惡意程式或是搜集你的個資，大家務必小心。

另外，在測試版進入 iOS 13 其實比較沒有意義的部分是，理論上開發者在 iOS 13 發佈（九月）後才能提交經由新的開發工具包（SDK）開發的程式，也就是說大部分程式都還沒有針對 iOS 13 做最佳化（例如自動的夜晚模式 (Dark Mode) 就不太會出現在第三方的程式中），因此大家沒有特別對官方程式有興趣的話，還是先等等，才可以確保最好的使用者體驗喔！

## 二，談到安全性，新的 iOS 在隱私權上有重大提升

這次的 iOS 對於隱私權的管理上有重大的提升，包含 Apple 免費提供經由 iCloud 的 10 天（加密過的）監視影像雲端存儲以及確保處理都在本地進行（例如動態偵測等等，都在本地做好處理，確保不會把資料傳到第三方的伺服器處理而產生安全性疑慮），還有新的 HomeKit 路由器（分享器）。

以上是科技人才會比較知道的東西，但是對於一般使用者來說，一些很基礎的服務也有重大突破。例如定位資訊上，以往的選項是「一直開啟」、「在程式運行的時候開啟」跟「不允許」，現在你的預設選項少了「一直開啟」，並提供大家「只開啟一次」的選擇，讓你可以更知道這些科技公司什麼時候在拿你的資料。要使用「一直開啟」的選項，就必須進到隱私權設定裡面去更改。

![](https://i.imgur.com/vfKIfjx.png)

有些公司會藉由 Wi-Fi 跟藍芽去推測你的位置，現在你在 iOS 13 中也會看到一個問題問你要不要讓它存取你的藍芽，大大降低第三方透過這種方式「跟蹤你」的可能性。

另外一個重大的突破還有用 Apple 登入，簡單來說就是 Apple 幫你建立一個一次性帳號，如果要提供 email 的地方，你可以選擇用 Apple 的一個將 email 轉寄到你的 email 的獨特加密帳號，因此這些公司就不會知道你的 email 帳號，當你不想要收到來自這個公司的信件，只要取消這個帳號的轉寄就可以了。

## 三，Memoji 貼圖

以往 Animoji & Memoji 只能在有 Face ID 的機種才能只用，這次增加了一個 Memoji 貼圖的程式，在所有能更新到 iOS 13 的裝置都能「吃得到」。基本上就是你現在也可以設定自己的 Memoji ，並且可以使用一些預設的 Memoji, Animoji 動作，當作貼圖使用 — — 酷的是這個功能是在第三方程式中也可以使用的，實際運行起來就是會變成一張圖片傳送出去給你的朋友。

![](https://i.imgur.com/Agc4DiR.png)

## 四，程式頁面的重新設計

這次，如同先前外流的，提醒事項、照片編輯跟截圖編輯的頁面都有更新，整體的使用經驗感覺流暢、現代很多。而提醒事項也外加了一些放圖片、智慧型辨認時間、頻率的功能，使用起來應該會方便很多。

![](https://i.imgur.com/GPIiAUs.png)

另外，音量控制面板是 iOS 一直被人詬病的部分，大家認為實在沒有必要調整音量的時候把整個螢幕擋住，而這次也像謠傳的一樣，終於更新了這個部分。

![](https://i.imgur.com/Zeyv9mA.png)

## 五，語音控制 — — 很有潛力的輔助使用功能

藉由顯示數字、點按哪個部分的指令，甚至是「截圖」的指令，可以在「不用手」的狀況下使用你的手機，對於行動不便的使用者來說實在是一個很有用的功能 — — 連我在試用的時候都覺得這功能意外的準確，整體經驗是會覺得「好用」而不只是「對特定族群很方便」的感覺而已。

![](https://i.imgur.com/Z6YI0eA.png)

## 六，對了， iPad 獨立了 — — iPadOS 13

iPad 這次有一個新的作業系統名稱叫做 iPadOS，基本上是針對大螢幕改造版的新的 iOS，雖然目前整個基底（甚至是 Build Number）都還是 iOS，但是是一個發展潛力十足的系統。包含多視窗的多功、新的主畫面、重新設計的「檔案」程式，經由 USB 使用滑鼠（輔助使用功能）跟輸入相機照片，甚至作為 macOS 的輔助螢幕（Sidecar），甚至是號稱有桌面級的 Safari 升級，還有從 App Store 下載字型、用手勢複製貼上，更「有反應」的 Apple Pencil，整體來說聽起來都是很有發展潛力的作業系統。

![](https://i.imgur.com/Sudxrrw.jpg)

## 七，macOS Catalina

以往 macOS 都是使用 iTunes 進行同步裝置的工作，但是仔細想想這個邏輯其實挺奇怪的，因此這次在 iTunes 要被變成「小 macOS」之前 Apple 把 iTunes 除掉，分割成 Music, Podcasts, Apple TV 三個程式之餘，便將同步的功能移動到 Finder 程式中。

![](https://i.imgur.com/Vmp4TNR.png)

這個轉變其實不只解決掉了 iTunes 功能太多的問題，也是讓真的該放在 Finder （檔案管理系統）的東西「回歸」到它該去的地方。

另外，之前謠傳的 Sidecar 程式，不只是一個代號，而是真的變成了一個 macOS 的功能。

![](https://i.imgur.com/pjkV1eX.png)

現在在 macOS 的系統偏好設定中，可以選擇這個 Sidecar 的選項，也就可以從這裡將你的螢幕投放到（應該是執行 iPadOS 的） iPad 上，你就可以讓你的 iPad 真正變成一個延伸螢幕。

而 [Marzipan 計畫]({{site.url}}{{site.baseurl}}/posts/2019/Apple-Marzipan.html)也換了個名字，變成 Project Catalyst，讓開發者可以輕鬆將 UIKit 的程式也變成一個 Mac 程式。已經有許多廠商（包含 Twitter）宣布將藉由 Project Catalyst 將 Twitter 程式搬運到 macOS 上供使用者使用。

![](https://i.imgur.com/AOTkGXI.png)

在測試過程中也意外發現，新版的 macOS 截圖後，可以直接從右下角的圖示 drag-and-drop 了，也就是說截圖完之後不用等到圖片在桌面上出現才能夠使用在文件中了！

## 八，watchOS — — Apple Watch 也獨立了

現在下載 Watch App 不用再透過 iOS 裝置了，也就是說 Watch App 現在是一個新的類別，而不是 iOS App 的延伸了！

這一次 watchOS 6 不意外地多了一些新錶面，而且新錶面還挺好看的，同時對於健康功能的部分，新增了「活動趨勢」讓你知道你跟過去相比是更活躍還是更懶惰，而你的活動大綱也可以在 iOS 裝置上看得到。

同時這次新增了一些程式和聲音串流的 API，因此如果你很愛看體育競賽，現在也可以在新的版本中聽轉播、看比數。另外新的生理期週期紀錄的程式，除了紀錄的功能之外，也包含下次生理期可能來的時間的通知，以及一些讓生活更簡便的功能，跟過去相比起來這個 watchOS 的版本算是很豐富的一個新版本。

![](https://i.imgur.com/mjL8DVo.png)

## 九，tvOS 切換使用者

tvOS 的新版相對起來比較「無聊」一點，但是比較有感的是新增了一個可以簡單切換使用者的通知中心，跟 macOS 一樣座落在畫面的右邊。

![](https://i.imgur.com/paNywLP.jpg)

## 十，SwiftUI，這個框架強

Swift 現在有一個自己的新框架，可以快速用簡短的 code 生成比較大型、原本要花費很多精力的程式碼才能生成的巨大 UI。背後的實作都由 Apple 寫的程式去驅動，因此有新功能（例如夜晚模式 (Dark Mode) 這種新功能）也可以很快、甚至是自動就會運行了。

![](https://i.imgur.com/jS8qLXS.png)

![](https://i.imgur.com/E9Y107q.png)

以上就是本次為大家整理的十個 WWDC 發佈程式的重點，謝謝收看！(XD)