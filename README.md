# 名詞解釋＆心得
## position

### relative
- 離開原來的位置，定為點為原來的位置
  - 原來的位置還佔空間，移動到的位置可視為浮上來不佔位置
  - 位移參考的是原來位置的四個邊
  https://codepen.io/TengLee/pen/PKEQLZ




### abosolute
https://codepen.io/TengLee/pen/YrBvop
- 往父層找定位點，除了static以外，relative, absolute, fixed都可當定位點
五個步驟
1. 先從流浮上
2. 找父元素有無定位設定，除了static以外，relative, absolute, fixed都可定位
3. 當父元素有無定位設定會一直定位到window
4. 捲軸往下卷absolute會留在最一開始window的位置
https://codepen.io/TengLee/pen/braRXj



## verticle align
- 沒特別設定的話為baseline
- baseline: 默认。元素放置在父元素的基线上。
- middle: 把此元素放置在父元素的中部。
https://codepen.io/TengLee/pen/vJppdR?editors=1100



## float
http://zh-tw.learnlayout.com/clearfix.html
https://codepen.io/TengLee/pen/ZJvvBE
https://codepen.io/TengLee/pen/qXmwyz
- float使DOM浮起來，但又不會浮得高過後面DOM的Content，也就是會跟後面的文字同個高度才會造成文繞圖
- clearfix意思是避開浮動, 防止float溢出包含它的元素
- 父元素設overflow auto之所以可以包著子元素是因為overflow auto會去抓自元素的邊界
```
.clearfix {
  overflow: auto;
}
```



## ul / li
- li 水平排列：inline-block
- li 垂直排列：偽元素/line-height/flexbox
- li間之所有會有空隙，是因為有空格或斷行， 設ul font-size=0, li font-size再設回來即可
https://codepen.io/TengLee/pen/XaVEWP
- 去除點點：ul {list-style: none;}
- ul有預設padding-start:40px 和 margin-top/bottom:1em
- li 水平垂直平均分配位置：flexbox或下面做法
  ```
  ul {
    font-size: 0;
    padding: 0;
    width: 100%;
    list-style: none;
    li {
      display: inline-block;
      width: 20%;
      line-height: 80px;
      text-align: center;
      a {
        font-size: 16px;
      }
  }

  ```



## padding margin的心得
當同一階層 用margin 特別是margin-bottom
當不同階層 用padding 特別是padding-top



## margin
https://codepen.io/TengLee/pen/mMLOzz
- block: 元素垂直的margin會互相重疊, 並且會被父階層合併
- inline: 元素不會有垂直的margin
- inline-block: 元素垂直的margin，不會互相重疊．只有block會重疊
https://codepen.io/TengLee/pen/ayYPMd
- margin重叠通常出现在三种情形下
  - 第一种：既是上面举例的相邻两个兄弟元素
  - 第二种：父元素和第一个或者最后一个子元素
  - 第三种：空的block元素；
- margin-top重叠条件：
  1. 父元素费块状格式化上下文元素
  2. 父元素没有border-top和padding-top值
  3. 父元素和第一子元素没有inline元素分隔
- margin-bottom重叠条件：
  1. 父元素费块状格式化上下文元素
  2. 父元素没有border-bottom和padding-bottom值
  3. 父元素和最后一个元素没有inline元素分隔
  4. 父元素没有height相关的限制； 其实这些条件也是我们消除父子元素重叠的方式。


###  負margin
- 增加該DOM的空間
  - 寬：變胖   
  - margin-top：自己往上移
  - margin-bottom:下面的ＤＯＭ往上移

## Flexbox
-  flex 其實是由三個屬性組合而成，依照先後順序分別是「flex-grow」、「flex-shrink」和「flex-basis」，如果 flex 只填了一個數值 ( 無單位 )，那麼預設就是以 flex-grow 的方式呈現
  - flex-shrink：數字，無單位，當子元素的 flex-basis 長度「大」於它自己在父元素分配到的長度，按照數字做相對應的「壓縮」比例分配，預設值為 1，設為 0 的話不會進行彈性變化，不可為負值。
  - flex-basis：子元素的基本大小，作為父元素的大小比較基準，預設值為 0，也因為預設值為 0，所以沒有設定此屬性的時候，會以直接採用 flex-grow 屬性，flex-basis 也可以設為 auto，如果設為 auto，就表示子元素以自己的基本大小為單位。


### Variable width content
- Using the col-{breakpoint}-auto classes, columns can size itself based on the natural width of its content.  
- .col-sm-auto，表示在media大於sm寬度以上時，子元素的寬度由內容決定


### align-items
- align-items 決定了內容元素與整個 Flexbox 的「垂直對齊」位置


### align-self
- align-self 的作用在於覆寫已經套用 align-items 的屬性，如果照我們以前所寫，因為 align-items 是針對子元素，所以必須要用 align-self 來進行覆寫
- align-items 是針對內容為單行的元素進行處理


### align-content
- 如果遇到多行的元素，就要使用 align-content 這個屬性


### Horizontal alignment
- justify-content-sm-between, 表示在media大於sm寬度以上時，子元素排列方式為space-between


### No gutters
This removes the negative margins from .row and the horizontal padding from all immediate children columns.
```
.no-gutters {
  margin-right: 0;
  margin-left: 0;

  > .col,
  > [class*="col-"] {
    padding-right: 0;
    padding-left: 0;
  }
}
```

### Offsetting columns
- Move columns to the right using .offset-md-* classes. These classes increase the left margin of a column by * columns



## Navigation Bar
- https://v4-alpha.getbootstrap.com/components/navbar/
- Navbars require a wrapping .navbar with .navbar-toggleable-* for responsive collapsing and color scheme classes.
- .navbar-brand for your company, product, or **project name**.
- .navbar-nav for a **full-height and lightweight** navigation (including support for dropdowns).
- .navbar-toggler for use with our **collapse plugin** and other navigation toggling behaviors.
- .form-inline for any form controls and actions.
- .navbar-text for adding vertically centered strings of text.
- .collapse.navbar-collapse for **grouping and hiding navbar contents** by a parent breakpoint.



## background
- 越靠近螢幕，要寫在最前面，中間用逗號隔開
- 位置用百分比代替
- 結束時：零度是在右邊 90度是在上方

### 線性漸層
```
background: -webkit-linear-gradient(90deg , black, purple)
```

### 逕向漸層
```
background: -webkit-radial-gradient(ellipse , black, purple);
background: -webkit-radial-gradient(circle , black, purple)
```
- Ellipse (this is default):
- 越先寫的顏色越在中間





## z-index
- z-index要有position



## p
- 有預設margin-top/bottom:1em
- 可以用p自己做一個方塊
```
p {
  width: 300px;
  padding: 10px;
  margin: 15px auto;
  background-color: #303132;
  text-align: center;
}

p {
  margin: 0;
  text-align: center;
  background-color: #E3E3E3;
}
```



## a
- 去除底線：```text-decoration: none;```
- 常用
```
a {
  cursor: pointer;
  text-decoration: none;
}
```



## img
- 水平置中：margin-left, margin-right:auto



## mixin
- 就是函式，可以帶入引數和變數
- 幫你記住很多段落的程式碼
- 帶入變數的特性，來編譯出我們要的程式碼。
- @mixin是將程式碼帶入到對應的class去，同時可帶入變數。



## extend
- 如果你每個段落的CSS程式碼如果都長得一模一樣， 那你就把這段程式馬提取出來，每當需要用到時用@extend來呼叫
- 主要是拿來合併相同程式碼用的
- @extend則是藉由class合併，並吃到共通樣式，但沒辦法帶入變數。
- 所以如果你的樣式都固定不變的，不會需要用參數帶進去改變樣式的話，那就用@extend，程式碼會比較少些。



## 權重
- important! > inline-style > id > class > element
- eg:
  - form input[type=email] 12分
  - li.class[nth:child] 21分





# 有什麼狀況？？



## 水平置中
- block：margin-left, margin-right:auto
- inline, inline-block: 父階層用text-align: center



## 垂直置中
### 偽元素
- 適用: inline, inline-block
- 原理是偽元素會使div的vertical-align:center，所以div的base-line垂直置中，導致inline, inline-blockc垂直置中
- 偽元素本身就當作是一個「可自由調整大小的字或圖(inline元素)」
- 故inline多行會失敗
- 可修改inline和inline-block的vertical-align做變化
- 做法：
```
&::before {
content: '';
display:inline-block;
height: 100%;
vertical-align: middle;
}
```
https://codepen.io/TengLee/pen/dzJvNz


### abosolute margin:auto 上下左右為0
- 適用:
  - block(設定寬高)
  - inline-block(不可以沒有高，可以設固定寬高，fit-content, min-content, max-content)
- 做法：
```
.div {
  position: relative;
  div {
    position: absolute;
    top:0;
    bottom:0;
    left:0;
    right:0;
    margin: auto;
  }
}
```
- 上下左右＝0
- margin = auto
  - 當沒有設margin auto 變成抓不到邊界因此取預設值left=0, top=0移到左上
- 父層不能是static
https://codepen.io/TengLee/pen/braRXj


### line-height
- 適用:
  - inline
  - inline-block(height可設auto)
- 多行文字會失敗
- 做法：line-height的高設得跟div一樣高


### transform:translateY(-50%)
- 適用:全部
- 做法：
```
position: relative;
top:50%;
transform:translateY(-50%);
```


### flex
- 做法：父元素設定如下
```
div {
  display: flex;
  align-items: center;
  justify-content: center;
}
```
https://codepen.io/TengLee/pen/YxaaMX



### calc(), table



## 多個inline-block 水平垂直置中 偽元素
- 子原素皆設verticle-align;
- 偽元素之必要
```
::before {
content: '';
display:inline-block;
height: 100%;
vertical-align: middle;
}
```
https://codepen.io/TengLee/pen/vJppdR



## 整齊的格子
- 用table可以輕易弄出整齊的格子



## DOM高
- 決定高要注意，當固定div的高，內容超出高跑版
- 所以可以用min-height防止踩雷
- 全螢幕：100vh



## css 去除瀏覽器預設
```
html {
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
}
```



## body 跟 html多高？
- 首先要知道div外層包著body包著html包著window
- window 和 body的高度如果內容物有高度則有多高就有高
- 如果無內容物則為零，在window上方
- 渲染body background會渲染在window
https://codepen.io/TengLee/pen/BdJQWy



## 解決img下的多餘空白
- 1、將圖片轉換為塊級對像
- 2、設置圖片的垂直對齊方式
- 3、設置父對象的文字大小為0px
- 4、改變父對象的屬性
- 5、設置圖片的浮動屬性
- 6、取消圖片標籤和其父對象的最後一個結束標籤之間的空格。
http://dancewing.pixnet.net/blog/post/24572377-%E8%A7%A3%E6%B1%BAimg%E4%B8%8B%E7%9A%84%E5%A4%9A%E9%A4%98%E7%A9%BA%E7%99%BD



## 排版-變動寬度＆固定寬度
- 當一個父元素div為變動寬度，他的子元素一為固定寬，另一為變動寬度，除了用grid system，還有以下三種方法：
https://codepen.io/TengLee/pen/OxKvxV
- flex, calc(), float搭配margin
```
.flex {
  .post {
  display: flex;
  }
  .postDetail {
    flex: 1;
  }
}


.calc {
  .time {
    display: inline-block;    
    vertical-align: top;
  }
  .postDetail{
    display: inline-block;
    width: calc(100% - 80px);
  }
}



.floatMargin {
  .time {
    float: left;
  }
  .postDetail{
    margin-left:60px;
  }
}
```


## 在瀏覽器修改
- document.designMode = 'on'
