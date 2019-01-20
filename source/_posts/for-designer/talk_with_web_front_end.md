---
title: 網頁前端規格建議
date: 2017-06-23 22:04:32
tags: '團隊溝通技巧'
categories: '給平面設計師的'
---

# 給平面設計師的: 網頁前端規格建議

![](https://i.imgur.com/UvHo0gv.png)

這個文章不是給設計師跨前端用的。而是給設計師與前端工程師溝通用的。先說，我是以前端工程師的角度來看待這樣的情況。

## 緣起

案子的設計師給的畫面尺寸圖，工程師想看見的是
1. 量化的顏色標示(色碼)
1. 量化的距離單位(`em`, `px`, `pt`)
1. 量化的比例關係(`vh`, `vw`, `%`)
1. 對齊標示、有邏輯的RWD結果
1. ...

但是設計師的設計稿的形成過程，腦海中沒有太多的規格數字，而畫面元素關係、美感的掌握才是重點。

若設計師出圖缺乏工程師需要的資訊，工程師往往需要猜測(腦補)、運算...才能接近原稿上「畫面元素關係」，也無法得知設計師想表達什麼。

設計師出圖之後，看見工程師做出來的東西，總是會在心中吶喊著「照著圖做很困難嗎？」
然後工程師一直都沒有辦法忠實的表達設計師的想法，而設計師反而硬是給出的尺寸規格，總是依照目前尺寸圖面給的一些`數字+單位`而已。

## 作品載體的改變

<iframe height='307' scrolling='no' title='testFontSize' src='//codepen.io/dwatow/embed/OgjXWp/?height=307&theme-id=light&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/dwatow/pen/OgjXWp/'>testFontSize</a> by chris (<a href='https://codepen.io/dwatow'>@dwatow</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

^codepad裡給的^ ^inch^ ^和^ ^cm^ ^，值都是給^ ^0.1^ ^，物理單位可以拿尺來量。^

### 工業 & 平面設計

設計師受的訓練，是將畫面元素品味化、感覺化的角色，美感是設計師收服客戶的利刃。而且在平面設計的傳統訓練中，作品載體本身並不會有變化，通常是物理介質，像是金屬、壓克力、帆布以及最常見的紙，使用的單位也有一套真實世界的表示方式。

**精細度**: `dpi`
**尺寸大小**: `pt`, 公制 (`cm`, `mm`), 英制 (`inch`)
...

### UI 設計

但是在網頁、UI設計的領域中，相同的地方一樣是對美感的掌握與元素間的關係...等抽象的表達能力，最大的不同在於數位媒介，這種「材料」的熟悉度與掌握，是最大的關鍵，往往也讓設計師覺得「我又不是工程師，為什麼要看原始碼」。

**精細度**: ppi
**尺寸大小**: px, pt, em, ex...等

:::danger
對於常常接網站設計的設計師來，這些東西既不熟悉原理又常見，往往是靠這些不熟的東西和工程師進行溝通，但是又覺得這種術語是程式語言，應該和平面設計無關....

但是岐見往往就在這些地方，造成溝通落差的也就在這裡
:::

# 建議的做法

## 給設計師的建議

![](https://i.imgur.com/jmYtoLZ.png)

設計師要標示尺寸規格時，簡單的分成幾種

- 對齊輔助線(加上文字描述)
- 比例(無單位)
- 距離(選用熟悉單位)

由於網頁是會在各式解析度顯示相同畫面的一種平面媒介，所以縮放、改變大小是很正常，標示上必須要表達
「這個距離，這在畫面縮小時，可縮小」
「這個距離，這在畫面縮小時，不可縮小」
「這個距離，若畫面擠壓到不可縮小的元素時，改成手機版排版」
「這個元素，放置的位置，是因為對齊哪個基準...」
「這個元素，放置的位置，是因為留白多少」
之類的...

:::info
好的工程師會透過「對齊邏輯」去抓出「數據規格」
:::

### 必定標示的

- 每個要「固定大小的元素」長寬
- 整個畫面的寬度(設計稿基於多少解析度的螢幕？)

## 給前端工程師的建議

千萬不要硬是要求設計師將這些通通都了解，這...太困難了。對他們而言這很瑣碎又不常用，久了設計師也就忘了。

### 回覆需要的尺寸給設計師

![](https://i.imgur.com/NPoBsoT.png)

這是必然的一步。設計師不知道施工需要的尺寸是哪一段到哪一段。
工程師要畫箭頭給設計師標示，而且要預計對方只會給你 `px` 值。

例如: 設計師不會知道 `position: absolute` 不佔空間，不可以把它當參考點標示。

# 口述的做法
省掉設計師標示步驟

> 因為我不是設計師，我也無法要求設計師做什麼。
> 但是我是程師，所以，我可以建議我自己能做什麼。

前端工程師可以盡量了解設計師對於畫面的「定位關係」前後邏輯。如果不行就聽聽設計師如何建構這個畫面的描述吧，聽他用自己的話描述一次。

設計師最常見是靠幾種方式:

- 對齊定位
- 比例定位
- 品味定位

靠「對齊」和「比例」在處理畫面元素，而這也是最具邏輯的表示方式，這一點要好好在每次溝通的機會盡量問設計師，了解後也方便將它轉化為量化規格。

剩下的就是「品味」的問題，就...靠視覺了，不過要使用一項之前，必須詢問品味達成的環境規格。(寬度解析度？螢幕？)

例如: 在**fullHD**的畫面之下，這兩個色塊之間的關係如圖(不標示尺寸)，畢竟有些元素關係就算標示了尺寸也沒有實質的效用。

## 若平面設計師想~~認識的 RWD~~ 跨 UI 設計的建議

針對網頁`RWD`的特性出現的幾個規格要...過目。
`vh`, `vw`, `em`, `rem`。^[[CSS Unit](https://www.w3schools.com/CSSref/CSS_units.asp)]

# 還是要溝通!!

上述給設計師與工程師的建議，如果都盡力了，並不代表之後不用溝通了，而是盡可能的增進工作效率。
也不代表完全靠圖溝通，希望可以快快樂樂的工作，不要把太多的時間花在這種可以預測、可以避免、可以變小的問題上呀！