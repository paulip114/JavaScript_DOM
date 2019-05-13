# Javascript_DOM
DOM 架構

<img src="https://github.com/paulip114/Javascript_DOM/blob/master/domarchitecture_thumb2.png">

透過 DOM 的操作，可以重構整個 HTML 檔案，可任意添加、移除、改變其項目，上方那張橘色的圖即為 DOM 之完整架構圖，最上方是 Core ( DOM Level 1) ，再下來是 XML 、 HTML (DOM Level 2)，甚至以下有許多的 Event (DOM Level 3)，最下方是使用者端的 Event ，主要分為以下三種：

(1) KeyboardEvents ：鍵盤事件
(2) TextEvent ：文字事件
(3) MouseEvents：滑鼠事件

由於 DOM 是由節點組成的，故一個 DOM 的物件 ( ex. html 檔) 可能可以看成以下架構，即所有的 Node 組成了一個檔案數，HTML 裡面的每個元素、屬性、內容等都代表著其中一個節點，並不斷延伸：

<img src="https://github.com/paulip114/Javascript_DOM/blob/master/ct_htmltree_thumb3.gif">

DOM 操作基本語法

操作語法最常用以下幾項：

(1) `getElementById()`

用法為

```javascript 
document.getElementById("ID");
```

例如

```javascript 
var choose = document.getElementById(‘choose’);
```

可以取出 HTML 內容當中 `<div id=”choose”> test </div>` 當中的 `test` 字串
ps. 此項目無法使用在 XML 檔案當中

(2) `getElementsByTagName()`

用法為

```javascript 
document.getElementsByTagName("標籤名稱");
```

例如

```javascript 
document.getElementsByTagName("p");
```

將會回傳文件當中的所有 `<p>` 元素內之內容
ps. 原本還有 `getElementByNAme`，但是在新版本的 DOM 中已被移除

使用 DOM 變數之內容

如果要把之前的內容取出，則可使用

```javascript 
var x=document.getElementsByTagName("p");
```

會將 `<p>` 裡面的內容，丟進 x 變數當中

如果有一個以上的 `<p>` 資料的話，則可以使用以下代碼 loop 取出資料
  
```javascript 
var x=document.getElementsByTagName("p");for (var i=0;i<x.length;i++){   // do something with each paragraph}
```

如果只取出特定項目，例如第4個項目，則可使用以下代碼

```javascript 
var y = x[3];
```

動態變更 HTML 的內容
現在在 html 當中有一行為

`<div id=”content”> test </div>`

如果要利用 JavaScript 更改內容的值，可使用以下代碼

```javascript 
var x = document.getElementById(“content”);
x.innerHTML = “newContent”;
```

如此一來，原本的 `test` 就會更改為新的內容，即 `newContent`

設定 Tag 屬性

我們有時候會需要針對 HTML 當中的 tag 新增一些屬性，可使用以下代碼

```javascript 
document.getElementById(‘choose’).style.fontWeight = ‘bold’;
```

上面那行的意思是說，針對 HTML 當中的 `<div id=’choose’> test </div>` 的 `test` ，新增粗體文字屬性

一個簡單的範例

```javascript 
var choose = document.getElementById(‘choose’);
```

0

以上範例的意思就是，在網頁上面顯示一段話：「請按我」，【請按我觀看範例】
透過 `getElementById` 取得 DOM 物件內容，並透過 `getValue` 連結 JavaScipt
使用 alert 將結果顯示，即可完成

相關工具
JS split method ：將 DOM 物件內容取出後，再針對內容做切割
http://www.w3schools.com/jsref/jsref\_split.asp

JS RegExp Object ：使用 Regular Expression 的方式，取出 DOM 之內容
http://www.w3schools.com/jsref/jsref\_obj\_regexp.asp

jsoup ：用 Java 寫成的 HTML Parser
http://jsoup.org/

