---
layout: post
title:  "Apple 的 Marzipan 計畫"
date:   2019-04-17 12:00:00 +0800
background: 'https://i.imgur.com/ZqTcSCx.png'
categories: 技術名詞小解析
---
在去年 WWDC （Apple 六月活動：全球開發者大會）時，Apple 公佈了一個很多人**懷疑已久**的計畫。一直以來都有人在問蘋果會不會終歸把 macOS 和 iOS 兩個平台合而為一，蘋果的答案則是很簡單的：

![](https://i.imgur.com/ZqTcSCx.png)

但是同一時間，Apple 也透露了正在發展一個技術，要讓 macOS 上面也可以運行 iOS 的程式，他們初步把 Apple News、Stock（股市）、Voice Memos（語音備忘錄）、Home（家庭）四個 iOS 程式移植到 macOS Mojave 作為實驗，也跟開發者們說 2019 年將這個「Marzipan 計畫」進一步延伸到 App 開發者這一線。

![](https://i.imgur.com/WyDCLIy.png)

## 移植大概是什麼意思？

如果有過 macOS 跟 iOS 開發經驗的人，大概都知道上圖中的一些用語。macOS 跟 iOS 其實在基底上是相同的，二者的差異只在於 macOS 使用的是 AppKit 這個框架，而 iOS 使用的是 UIKit 這個框架，也就是說前者是為了設計桌上型電腦程式所開發的框架、後者則是為了開發行動程式所開發的框架。

而 Marzipan 計畫所做的事情，就是把上述原來只用於 iOS 的 UIKit 也在 macOS 上準備一份，變成上圖中的狀態，所以在 macOS 如此一來，除了一些 App 表現的不同要特別在程式碼中寫出來，大部分的東西都可以直接一個 move 過來 macOS。

## 移植出來是什麼樣子？

講到這邊如果還沒有看過呈現結果，你大概會出現的疑問是，move 過來會長成什麼樣子？是會長得像 macOS 中塞一個 iOS 模擬器的樣子嗎？你會有這樣的疑問是很正常的，因為確實有很多種不一樣的實現方法，不過幸運的是，我們上面有提到Apple 的第一階段已經透過上面提及的四個程式呈現給大家了。

如果你是有使用 iOS 裝置和 macOS 裝置，只要打開 macOS 上的 Apple News（新聞，台灣未開放）、Stock（股市）、Voice Memo（語音備忘錄）、Home（家庭）四個程式，你就可以看到呈現出來大概是什麼效果，我以下以 Voice Memos（語音備忘錄） 這個程式呈現，給大家一點概念：

![](https://i.imgur.com/lomgDWZ.png)

因為 iOS 以及 UIKit 原來開發的程式，是為了觸控螢幕的行動裝置設計的，所以直接整個 move 過來，在滑鼠控制的 macOS 系統下，可能會有點怪怪的、不太好用。因此移植過來應該會有一些特殊的詮釋方式，呈現出一種新的 macOS 視窗風格（與原來 AppKit 的程式感覺還是會有些不同）。

## 下一波會發生什麼事

因為蘋果有說在 2019 年就會將這個 Marzipan 計畫進一步開放給開發者使用，所以可以預期今年 WWDC 以後會慢慢有一些開發者往這個方向去開發，但是數量跟速度上，應該都不會太多、太快（在觀點區會討論一下數量的部分），而 macOS 10.15 （下一版）前幾天已經[傳出](https://9to5mac.com/2019/04/10/macos-10-15-itunes-standalone-apps/)下一波應該會把 iTunes 拆成 Music（音樂）、Podcast（播客）、TV（電視）三個應該會是 Marzipan 計畫的程式，以及 Books（書籍）應該也會有一個新的、 Marzipan 計畫下的更新。

## 觀點與分析

基本上 Marzipan 計畫讓 iOS 開發者可以簡單地把 iOS 上的程式運到 macOS 上面，這個動作對於 macOS，尤其是 Mac App Store 的程式開發環境應該會是比較好的。首先是取決於 Apple 如何規定，如果 Marzipan 程式有限定只能使用 Mac App Store 販售或發佈，那麼有機會快速解決 Mac App Store 的程式的多樣性跟數量遠遠不及 iOS App Store 的問題。但是即便沒有這樣的規定，只要 iOS 的開發者可以簡單的把程式運過去 Mac、不用重新設計整個程式，相信開發者們也會滿有意願把程式運過去 macOS 使用。

### 為什麼我會說數量太多

對，我確實是說數量不會太多，為什麼呢？如果不是開發者的人可能不知道，要寫出一個程式並不是只有原生程式一招，其實市場上本身就有很多的框架，讓你可以用 C++ 或是其它語言，一次寫好無論是 iOS 跟 Android，或是桌上型平台的程式。這些框架基本上是在編譯的時候把程式碼運用他們自己的方式，翻譯成你的手機可以讀的程式，因為用的大致上都不是原生的 UI，你就會發現這些程式的 UI 運行跟其它程式的邏輯會有一點差異。

怎麼辨別這一種程式，如果你發現一個程式在 iOS 跟 Android 都有、而且運行方式跟外觀幾乎一模一樣，那這個程式有滿大的機率並不是一個原生的程式。而這樣子的程式因為很有可能並不是用 iOS 原生的寫法寫出來的，Marzipan 計畫的發佈對於這些開發者來說，因為用不到所以幾乎等於什麼事都沒有發生。當然這樣的框架可能本來就有支援搬運到 macOS 的功能，或是可能這些框架會因為 Marzipan 計畫而轉向、得以發展這樣的功能也是有可能，但是這些事情因為未必會發生，所以我們也只能繼續看下去。

再來就是有一種 iOS 程式大概也不會被搬運到 macOS 上，也就是那些你看起來很久沒有維護，或是使用者 UI 上已經很久沒有更新，看起來特別大（在大螢幕手機上）或是在 iPhone X, Xs, Xs Max 上有很大的黑色相框的程式，這些程式基本有很多種可能，有可能他是整個 UI 自己寫的，所以要配合不一樣的螢幕可能要做大量的程式碼調整；也有可能這樣的程式是用一個比較舊版的程式語言（例如版本較舊的 Swift），可能開發者的系統沒有進行更新所以 Xcode 的版本比較舊、SDK（軟體開發工具包）沒有進行更新⋯⋯等等諸多的可能性，造成 Marzipan 這個計畫基本上對於這些開發者要不是用不到，就是太麻煩，這種情況下，對於這些程式移植的機會跟意願，還是可以預期是會比較低的。

最後我們也不知道目前 Marzipan 的完成度跟複雜程度，如果太過複雜或完成度太低，相信願意移植的開發者也會比較少，不過整體來說，我覺得 Marzipan 專案還是值得期待的。