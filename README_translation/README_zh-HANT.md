# Rime古諺文輸入方案

譯文：[简体中文](../README.md)

## 簡介

這是一個基於[Rime](https://rime.im/)的古諺文輸入方案。可以以形碼的方式，方便地輸入古諺文字符和傍點。用戶還可以根據喜好，對輸出字元進行四種模式的調整。

## 特性

- 四種可選的輸出模式

  由於古諺文基本是由Hangul Jamo及其擴展區字元以初聲（초성, Choseong）、中聲（중성, Jungseong）和可選的終聲（종성, Jongseong）組合而成的，且Unicode有較為複雜的等價變換處理。

  1. 無變換（무변환）

     僅輸出原始古諺文字母，不合併輸出結果中可以合併為諺文音節的部分。

  2. NFC變換

     對輸出結果進行NFC變換。具體可參見Wikipedia\`[Unicode等價性](https://zh.wikipedia.org/w/index.php?title=Unicode%E7%AD%89%E5%83%B9%E6%80%A7&oldformat=true)\`條目。

  3. NFKC變換

     對輸出結果進行NFKC變換。具體可參見Wikipedia\`[Unicode等價性](https://zh.wikipedia.org/w/index.php?title=Unicode%E7%AD%89%E5%83%B9%E6%80%A7&oldformat=true)\`條目。

  4. 僅變換單個字元

     僅將輸出結果中，可以合併為單個諺文音節的內容進行變換。

- 支援傍點輸出
- 支援Unicode已收錄的所有諺文字母
  1. [Hangul Jamo](https://www.unicode.org/charts/PDF/UA960.pdf)
  2. [Hangul Jamo Extended-A](https://www.unicode.org/charts/PDF/UA960.pdf)
  3. [Hangul Jamo Extended-B](https://www.unicode.org/charts/PDF/UD7B0.pdf)

- 在組合狀態下，支援Unicode已收錄的所有諺文音節組合

  [Hangul Syllables](https://www.unicode.org/charts/PDF/UAC00.pdf)

## 安裝指南

1. 安裝好對應平台的輸入法（安裝地址見[Rime官方下載頁](https://rime.im/download/)）；

2. 將`yeshangulMT.schema.yaml`和`yeshangulMT.dict.yaml`添加到用戶文件夾；
3. 將`json`文檔和`ocd2`文檔添加到程序文件夹的`data/opencc`目錄下；
4. 重新部署您的輸入法
5. 切換到`옛한글_MT`使用輸入法

## 使用說明

### 鍵盤佈局

<figure>
    <img src="../src/keyboard_layout.svg" alt="圖1. 鍵盤佈局">
    <figcaption style="text-align: center; color: rgba(0, 0, 0, 60%); font-size: 0.85em">圖1. 鍵盤佈局</figcaption>
</figure>



鍵盤佈局參考了GitHub倉庫\`[5hwb/Old-Hangul-Input-Method](https://github.com/5hwb/Old-Hangul-Input-Method)\`。以下做出些许解释：

- `S`對應的是“ㅱ”“ㅸ”“ㅹ”“ㆄ”下方的小圓圈。以上四個字母在本輸入法中的擊鍵分別是`aS`、`qS`、`QS`、`vS`。
- `F`和`H`對應的是傍点“〮”和“〯”
- `Y`为初聲填充符，`U`为中聲填充符。這裡的`J`標註了“F”，根據對稱性，其應當是作為終聲填充符；然而Unicode並沒有這樣的字元，且其功能与分詞符無異，故J可作為分詞功能存在。
- 方案中雖然存在雙子音，但是僅限於初聲或終聲中的第一個雙子音可以用單鍵打出。比如“ㅆ”可以用`T`打出，“ㅹ”可以用`QS`打出，但是“ᄥ”要透過`qtt`打出，而不能透過`qT`打出。

### 輸出模式切換

輸入法配置了四種輸出模式，可在方案選單中找到切換開關。

## 貢獻

可透過Pull Request來進行代碼貢獻和Issue來提出問題。

## 协议

以MIT協議發佈。