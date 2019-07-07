---
layout: post
title:  "把網頁變成程式：Electron 與 Nativefier"
date:   2019-04-24 12:00:00 +0800
background: 'https://i.imgur.com/jJW8yuK.png'
categories: 技術說說看
---
**警告：本篇內容較深入，但是我們盡量說人話。**

上次在討論 Apple 的 [Marzipan（杏仁糖）計畫]({{site.url}}{{site.baseurl}}/posts/2019/Apple-Marzipan.html)的時候，曾經雖然提過 macOS 大部分的程式是用 AppKit 開發、 iOS 大部分的程式是用 UIKit 開發，這種開發工具包基本上就是官方幫你定義好（很大）一部分的東西，然後開發者有點像**玩積木一樣**把積木拼湊成你想要的功能，這通常就是開發的過程。

## 使用 AppKit 跟 UIKit 開發的優缺點

身為一個開發者，如果你要針對 iOS 或 macOS 開發一個程式，最直接、最直覺的方式，或許是透過 Xcode 跟上述的兩個框架來設計你的程式，但這不會是**完全沒有問題**的。雖然在最理想的狀況下，你設計出來的程式會跟作業系統的外觀、邏輯一致，只要你的程式碼夠有效率，效率上應該也會是最好的，畢竟這就是「完全為了」這個作業系統設計的，但是完全為了這個作業系統設計會有什麼缺點？對，就是**相容性問題**。

以電腦來說，如果今天是在整個市場上只有 macOS 一個作業系統、規格的情況之下，相容性問題應該不是大問題，但是顯然這不是市場上的真實狀況：至少在我們可見的範圍內，市場上至少有 Linux, macOS, Windows 三個規格組，如果你專門為了 macOS 設計了一個程式，你就會發現你的程式只能針對 macOS 這個平台。

好一點的狀況，你開發給 iOS 的 UIKit 程式可能可以藉由上篇提到的 Marzipan 計畫移植到 macOS 上，但是基本上 Android、Linux 跟 Windows 在上述的兩個情況下，都沒辦法享受到你寫的程式或是提供的服務。如果你只是一個小型的開發者，你的程式主要是為了自己使用，那麼你用 AppKit 或 UIKit 開發不會是個大問題，但是要是你是一家商業公司，而你的消費者可能用的是 macOS、也可能是 Windows 的使用者，你的手機程式可能要給 Android 的使用者使用、也可能要發佈給 iOS 的使用者怎麼辦？

我們在討論 Marzipan 的那篇最後的討論中有提到，事實上很多程式，並不是用所謂的原生的方式寫出來的，而事實上這也是對公司最簡便也最省錢的開發方式。以 macOS 的來說，如果你知道怎麼看一個 Mac App 的 info.plist 檔或是 Frameworks 資料夾，你就可以進去看一下，有時候真的可以看到這個是用什麼方式開發出來的。

![](https://i.imgur.com/e835WIa.png)

這三個程式應該算是使用我在 macOS 上比較常看到的三種工具包做出來的。由圖中可見，左上程式使用的應該是 **Qt** 這個開發工具組做出來的，左下因為是我自己開發的程式，可以很確定告訴大家是 Swift 的原生 macOS 程式，而從右邊的程式的 info.plist 中說到它是一個 AtomApplication，就可以知道這是一個 **Electron 程式**。

對鋪陳了這麼大一篇，終於要進重點了。

## 什麼是 Electron 程式

Electron 程式指的是使用 [Electron](https://electronjs.org) 這個框架設計出來的程式。Electron 是由 GitHub 為了製造他們的源碼編輯器 Atom 所設計出來的一個框架。用最簡單的語言來說，Electron 的概念就是—**嘿你有發現嗎？網頁沒有我們上面說的這個「相容性問題」耶！**

因為網頁前端（瀏覽器中看到的部分）的源碼是用 **Javascript 配合 HTML 跟 CSS** 做出來的，只要能夠讀懂這三種語言就可以呈現網頁的內容，因此每一個 Electron 程式都包著一個瀏覽器——而這個瀏覽器就是 Google 的 Chromium 瀏覽器（**對，就是 Google Chrome 瀏覽器**）。而後端的處理因為它使用的是一個可以用 Javascript 寫後端（一個網頁程式的伺服器、資料庫等看不到的地方）的執行環境 Node.js，因此你只要會寫 JavaScript 、會寫網頁，你就可以透過 Electron 寫出程式來。

一般的 Electron 程式是由 **Electron** 加上**本地的網頁檔案**做出來的**包著瀏覽器與網頁程式的桌上型程式**，但是既然它是**一個瀏覽器為底**的程式，冰雪聰明的觀眾朋友大概突然想問了 — —

**欸？既然「網頁」都可以變成「程式」，那麼那個我們可以用網址 (URL) 存取的網頁也可以變成程式嗎！**

對，可以。

## 這就要使用「忍術．Nativefier 專案」

因為網路上有人想到這個問題就一個突發奇想，於是 GitHub 上的 [Nativefier 專案](https://github.com/jiahaog/nativefier)就這樣誕生了。 Nativefier 基本上就是一個 **Electron 程式生成器**，所以生成出來的東西就是我們上面說到的這種 Electron 程式，而你只要在安裝了這個專案之後，終端機中輸入指令，你要的程式就這樣變出來了。

我們以下簡單示範**要怎麼不打一行程式碼做出一個 Nativefier 程式**。

![](https://i.imgur.com/H5FSl1z.png)

![](https://i.imgur.com/aDJJIpK.png)

![](https://i.imgur.com/z6fLmhl.png)


## 討論

上面講了這麼多，那現在來說說我的觀點吧。我覺得 Electron 基本上是一個好東西，Nativefier 基本上也是一個我有在用的專案，但是 Electron 也並不是完全沒有缺點。因為它底下是一個 Chromium 瀏覽器，所以 Chromium 比較大的缺點（例如可能比較吃資源一點），在 Electron 上可能也逃不掉。甚至可以看到一些原生程式的開發者，還會特地在他們的產品網站上註明「這不是一個 Electron 程式」。

![](https://i.imgur.com/Ntyn3zG.png)

不過總歸來說，以方便性來說， Electron 對於大部分的開發商來說，是一個省錢又方便的開發框架，對追求效能的開發者來說，可能就會不太喜歡這種「邪門歪道」 — — 至於以我自己來說，如果能有原生程式可以用，當然是以原生程式為主，至於 Electron 跟 Nativefier 大概就是一個「無魚蝦也好」的「下策」了！