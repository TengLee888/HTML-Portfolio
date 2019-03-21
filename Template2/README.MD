# HTML
### header
- 用flex align-items: center垂直置中
<br>

### banner
- 像banner這種一面都是圖的的可以用比例的距離，記得用**vh**
<br>


### bannerCenterBox
- 用absolute水平垂直置中
```
position: absolute;
top: 50%;
left: 50%;
margin-top: -111px;
margin-left: -300px;
width: 600px;
```
<br>


### .freeShipping p
- 像這裡如果要求灰色高是50px直接設p line-height: 50px就好了
<br>


### lowerContent
- 用flex 水平排列
- 設background-color分別為黑灰黑
<br>
<br>



## input
input有好幾個屬性
Type：決定是什麼input
value: 填了就有預設值
name: 會跟form data一起交，作為這個Form data的名稱



###button
給你一個按鈕，沒有default behaviors

### sumit
給你一個按鈕


# css
##background
要一次聲明多個屬性，<bg-size> 只能紧接着 <position> 出现，以"/"分割，如： "center/cover"

###background-size: cover
- 依比例圖片填滿畫面，依寬度，長度超過則會被裁切
<br>


###background-attachment
- fixed就是固定在畫面，不隨畫面滾動滾動

### background-position: center
- 當畫面縮小圖片還是置中
