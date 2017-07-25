# HTML
### header
- 這次讓Navigation Bar在上面
```
position: fixed;
z-index: 2;
width: 100%;
```
<br>


### banner
- 垂直置中
```
display: flex;
flex-direction: column;
justify-content: space-between;
```
<br>


### <div></div>
- 用這個小技巧可以在垂直置中的時候造製造空間
<br>


### arrow-down
- 網路上抄一抄就好了，關鍵字arrow
```
  position: absolute;
  left: 50%;
  transform: translate(-50%, 0%);
  width: 0;
  height: 0;
  border-left: 20px solid transparent;
  border-right: 20px solid transparent;
  border-top: 20px solid $pink;
  z-index: 1;
```
<br>


### <i>●</i>
<br>
