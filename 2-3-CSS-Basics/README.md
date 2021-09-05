### *Chương 2 & 3: Kiến thức CSS cơ bản phần 1 & 2*
# 13. CSS reset là gì ? Tại sao phải dùng reset CSS?

Do những thuộc tính mặc định của các trình duyệt khác nhau, --> reset CSS về mặc định để các trình duyệt hiển thị giống nhau.

# 14. Cấu trúc của 1 đoạn code trong CSS như thế nào?

```css
selector{
  property: value;
}
```
* selector: 
  * Tags: p, div, h1, main, a, span, ...
  * Class: .demo, .header,..
  * id: #container, ...
* property: color, background-color,...
* value: red, yellow,....

# 15. Tìm hiểu thuộc tính `color`, các giá trị về màu sắc cần nắm vững

`color` --> `hiển thị màu chữ`
```css
  /* value
  name: red, aqua, yellow
  hexa: #111 #ff7870 #7cd 
  rgb: rgb(0,0,0) rgb(255,255,255)
  rgba: rgba(0,0,0,0.5) 
  */
```

# 16. Nắm vững kiến thức về kích thước trong CSS

```css
.background{
  background-color: #2979ff;
  width: 200px;
  min-height: 200px;

  /* overflow: hidden; */
  /* overflow-y: auto; */
}
```

# 17. Làm hình nền với các thuộc tính về background

```css
background2{
  /* background-image: url("https://images.unsplash.com/photo-1626796615393-b6925bc1469b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1055&q=80"); */
  /* width: 100%;
  height: 1000px; */

  /* background-position: center; 
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed; */

  /* Viết gọn */
  background: url("https://images.unsplash.com/photo-1626796615393-b6925bc1469b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1055&q=80") fixed no-repeat center center / cover;
  width: 100vw;
  height: 100vh;
}
```

# 18. Các đơn vị trong css nên biết

`100vw` `100vh`

# 19. Đơn vị em và rem khác nhau như thế nào?

```css
/*
mặc định font-size tất cả trình duyệt 100% = 16px
1em = 1rem = 16px
*/
/* em là đơn vị phụ thuộc vào thuộc tính font-size của chính nó hoặc phần tử chứa nó */
.em{
  font-size: 32px; /* 1em = 32px */
  width: 10em;
  height: 10em;
  background-color: orange;
}
/* rem chỉ phụ thuộc vào font-size của thẻ html */
.rem{
  font-size: 32px;
  width: 10rem;
  height: 10rem;
  background-color: blue;
}
/* đưa về cơ số 10 cho dễ tính toán 
100% = 16px -> 62.5% = 10px -> set font-size: 62.5% để đưa rem vào dự án
lúc này, xét ở thẻ html
*/
html{
  font-size: 62.5%;
  /* 1em = 1rem = 10px */
}
/* hay sử dụng rem, linh động */
```

# 20. Thuộc tính về border cơ bản

```css
/* 
border: border-width border-style border-color;
border-width: ___
border-style: solid dashed dotted double 
border-color: ___
*/
.rem{
  font-size: 32px;
  width: 10rem;
  height: 10rem;
  background-color: palevioletred;
  border: 2px dashed purple;
}
/*  outline ~~ border
    nhưng outline ko có border-radius(bo góc)
*/
```

# 21. Nắm rõ thuộc tính margin

```css
.margin{
  width: 14rem;
  height: 14rem;
  background-color: #2979ff;
  /* margin: 10px; */
  margin-bottom: 80px;

  /* center - block tags */
  /* margin-left: auto;
  margin-right: auto;   */

  /* 1 giá trị: top = right = left = bottom = 20px */
  margin: 20px;
  /* 2 giá trị: top = bottom = 20px, right = left = 40px */
  margin: 20px 40px;
  /* 3 giá trị:  top = 10px right = left = 20px bottom = 30px*/
  margin: 10px 20px 30px;
  /* 4 giá trị: top = 10px, right = 20px, bottom = 30px, left = 40px */
  margin: 10px 20px 30px 40px;

  /* Margin có thể dùng số ÂM -> chạy ngược lại*/
  /* Padding ko dùng đc số ÂM */
}

/* .margin2{
  margin-top: 50px;
} */
/* chỉ hiển thị margin-bottom: 80px */
/* Vấn đề: margin collapse 
khi phần tử trên có margin-bottom phần tử dưới có margin-top thì sẽ lấy margin lớn hơn
-> chỉ lấy 1 giá trị margin
*/
```

# 22. Hiểu về thuộc tính padding

```css
.padding{
  width: 10rem;
  height: 10rem;
  background-color: palegoldenrod;
  margin: 0 auto;
  overflow: hidden;
  padding: 10px;

  /* 1 giá trị: top = right = left = bottom = 20px */
  padding: 20px;
  /* 2 giá trị: top = bottom = 20px, right = left = 40px */
  padding: 20px 40px;
  /* 3 giá trị:  top = 10px right = left = 20px bottom = 30px*/
  padding: 10px 20px 30px;
  /* 4 giá trị: top = 10px, right = 20px, bottom = 30px, left = 40px */
  padding: 10px 20px 30px 40px;

}
```

# 23. Tìm hiểu về box-sizing trong CSS

```css
.boxed{
  width: 10rem;
  height: 10rem;
  border: 5px solid black;
  padding: 1rem;
  background-color: gold;

  box-sizing: content-box; 
  /* giá trị mặc định của box-sizing, 130px
   width = width + padding-left+padding-right + margin-left+margin-right + border-left+border-right; 
   ~~height  
  100 + 10 + 10 + 5 + 5 = 130
  */
  box-sizing: border-box; 
  /* 100px 
  width = width - padding-left - padding-right - border-left - border-right;
  ~~height
  width = 100- 10 - 10 - 5 - 5 = 70
  + border + padding = 100
  */
}
*{
  box-sizing: border-box;
  /* tăng độ chính xác với kích thước */
}
```

# 24. Tìm hiểu thuộc tính display

```css
a{
  /* thẻ inline: width, height, margin-top, margin-bottom, float ko có tác dụng -> hạn chế về CSS*/
  text-decoration: none;
  color: white;
  width: 10rem;
  height: 10rem;
  padding: 1rem;
  background-color: black;
  display: inline-block;
}
```

# 25. Các thuộc tính liên quan tới Font cơ bản

```css
.font{
  font-family: 'Poppins', sans-serif;
  font-size: 1.6rem;
  font-weight: 300;
  font-style: italic;
}
```

# 26. Các thuộc tính liên quan tới chữ bạn cần biết

```css
.font{
  line-height: 1.4; /* khoảng cách giữa cách dòng */
  text-align: left;
  
  /* căn lề */
  /* text-align: right;
  text-align: center;
  text-align: justify; */
  
  /* max-width: 30rem;
  letter-spacing: 1px; 
  word-spacing: 2px;  */
  
  /* overflow: hidden; */
  /* văn bản chỉ nằm trên 1 dòng */
  /* white-space: nowrap;  */ 

  /* hiển thị dấu ... trên 1 hàng*/
  /* text-overflow: ellipsis;  */
  
  /* hiển thị dấu ... tới hàng thứ 3 */
  /* display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3; */
  /* một số trình duyệt sẽ hiển thị ko tốt -> dùng js tính toán số kí tự để hiển thị */

  /*ng dùng spam nhập 1 từ dính nhau thế này
    aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
    -> giao diện sẽ bị vỡ, và scroll ngang xuất hiện
  yêu cầu: vẫn rớt xuống hàng
  */
  word-break: break-all;
  word-break: break-word; /* recommended */
}
```

# 27. Tìm hiểu thuộc tính cho hình ảnh

```css
img{
  display: block;
  max-width: 100%; /* __recommended */
}
.image{
  width: 20rem;
  height: 20rem;
  
  object-fit: cover; /* hình đc tự động scale -> nét hơn */
  object-position: bottom; /* mặc định là center khi fit hình ảnh */
  
  margin: 0 auto; /* center, chỉ với display: block; */
  
  display: inline-block;
  border-radius: 50%;
}
.image-wrap{
  text-align: center; /* trick: đưa inline tag ra giữa */
}
```

# 28. Pseudo là gì ? Các pseudo cơ bản người mới học nên biết

```css
.pseudo{
  color: black;
  font-size: 5rem;
}
.pseudo:hover{
  color: orange;
}
.pseudo:active{
  color: red;
}
.pseudo:visited{
  color: #2979ff;
}
```

# 29. Bài tập chương 2 (Phần 1)

1. Tạo một khối có class là `box` có độ rộng và chiều cao lần lượt là `200x300` có màu nền là `#ffa400` và chữ bất kỳ màu đen, border màu vàng, padding 10px, margin 15px bo góc 4px, chữ canh giữa.

2. Tạo một khối có đoạn chữ rất dài bât kỳ, có độ rộng tối đa là `500px` hiển thị 3 hàng kết hợp dấu 3 chấm

3. Tạo một khối có đoạn chữ rất dài bât kỳ, có độ rộng tối đa là `100px` hiển thị 1 hàng kết hợp dấu 3 chấm

4. Tạo một khối có độ rộng và chiều cao lần lượt là `100vw` `100vh` cho hình nền bất kỳ, yêu cầu phủ toàn khối, canh góc bên phải, không có lặp lại

5. Tạo một khối có độ rộng và chiêu cao tương ứng là `400x400` và cho hình ảnh hiển thị bên trong, yêu cầu khối này là hình tròn, và hình ảnh nằm trọn bên trong, không được méo, không được tràn ra ngoài.

6. Chèn font từ Google vào bài tập sử dụng Fonts `Roboto` với các độ đậm là `400` và `600`

7. Tạo ra các button như hình: sử dụng padding, margin, text-align, kiến thức đã học
![https://designerup.co/blog/content/images/2019/01/button_corners.png](https://designerup.co/blog/content/images/2019/01/button_corners.png)

8. Tương tự bài 7 nhưng dùng thẻ `a`

9. Áp dụng pseudo `:hover` để khi rê chuột vào kết quả bài 8 thì đổi màu nền và màu chữ

## **[mySolution](.\exercises-1)**

***
***
# 31. Cách làm hình nền gradient, chữ gradient trong CSS

```css
.boxed{
  width: 20rem;
  height: 20rem;
  background-image: linear-gradient(to right bottom, #00aefd, #ffa400);
  /* 
  linear-gradient()
  direction: to right, to left, to bottom to top, to right bottom, to left bottom, to left top, to right top,  or 120deg
  color1
  color2
  */
}
.title{
  font-weight: bold;
  font-size: 3rem;
  background-image: linear-gradient(to left top, #ffa500, #00aefd );
  display: inline-block;
  margin-top: 2rem;
  margin-left: 2rem;
  color: transparent;
  -webkit-background-clip: text;
  background-clip: text;
}
```

# 32. Hiển thị 2 hình nền với background-image

```css
.background{
  width: 100vw;
  height: 100vh;
  background-image: linear-gradient(
    to bottom,
     rgba(255, 166, 0, 0.753),
      rgba(0, 173, 253, 0.699) 
      ),
      url("https://source.unsplash.com/random");
  background-repeat: no-repeat;
  background-size: cover;
}

```

# 33. caniuse là gì ? Và tại sao bạn nên biết

[https://caniuse.com/](https://caniuse.com/) là trang web check xem thuộc tính có hỗ trợ trên trình duyệt nào đó hay ko.

```css
.title{
  font-weight: bold;
  font-size: 3rem;
  display: inline-block;
  margin-top: 2rem;
  margin-left: 2rem;
  /* color: transparent;
  background-image: linear-gradient(to left top, #ffa500, #00aefd );
  -webkit-background-clip: text;
  background-clip: text; */
  color:blue;
}
@supports (-webkit-background-clip: text){
  .title{
    color: transparent;
    background-image: linear-gradient(to left top, #ffa500, #00aefd );
    -webkit-background-clip: text;
    background-clip: text;
  }
} /*nếu trình duyệt có hỗ trợ thì text sẽ màu gradient, những trình duyệt ko hỗ trợ thì hiển thị màu blue*/
```

# 34. Sự khác nhau giữa 3 thuộc tính opacity: 0, display:none, visibility:hidden

* `opacity: 0 ;` trong suốt nhưng vẫn chiếm diện tích, vẫn có thể nhắn vào ô đc.
* `visibility: hidden;` 
    * trong suốt, vẫn chiếm diện tích nhưng ko nhấn vào ô đc nữa
    * hay đi cùng với `opacity` để tạo hiệu ứng, transition, nhấn vào để xuất hiện vật
* `display: none;` biến mất hoàn toàn

# 35. Tìm hiểu về shadow trong CSS

```css
.shadow{
  width: 20rem;
  height: 20rem;
  background-color: #000;
  margin: 5rem auto;
  /* box-shadow: x y blur(mờ) scale(mặc định bằng kích thước ô) color; */
  box-shadow: 20px -20px 0px 0px rgba(255, 0, 0, 0.534);
}
.text-shadow{
  font-size: 5rem;
  font-weight: bold;
  text-shadow: 20px -20px 0px palevioletred;
}
```
**Customizing `box-shadow` on ChromeDevTools, similar with `text-shadow`**

![box-shadow-on-chrome](.\example2\box-shadow-on-chrome.png)

# 36. Sử dụng biến trong CSS như thế nào?

```css
/* Sử dụng biến để dùng chung ở nhiều nơi và thuận tiện sửa giá trị */
:root{
  --primary-color: #00aefd;
  --secondary-color: #ffa500;
}
/* var(--primary-color); */
```

# 37. Hiểu rõ về độ ưu tiên trong CSS, xác định độ ưu tiên trong CSS đơn giản với VSCode

```css
/* Độ ưu tiên trong CSS */
h2{
  color: crimson !important;
}
/* Tag < Class < Id< !important
    đánh dấu thuộc tính quan trọng -> ưu tiên nhất
    hạn chế sử dụng important
*/

/* Tag < Class < Id < inline-style < !important 
    style=" color: blueviolet; "
*/

#titlee{
  color: palevioletred;
}
/* Tag < Class < Id */

.titlee{
  color: aquamarine; 
}
/* Tag < Class
-> Class sẽ đc ưu tiên hơn Tag -> chữ màu xanh lá */

h2.titlee{
  color: #00aefd;
} 
/* ưu tiên cao hơn Tag */

h2{
  color: #00aefd;
} 
/* -> selectors cùng cấp, thì cái ở dưới sẽ ddc ưu tiên hơn -> chữ màu xanh*/


h2{
  font-size: 5rem;
  font-weight: bold;
  color: orange;
}

```
* xác định độ ưu tiên trong CSS đơn giản với VSCode
  * ```css
      /* 
      xác định độ ưu tiên trong CSS đơn giản với VSCode
      (x,y,z) ->(tag, class or attribute, id)

      0 0 1 tag
      0 1 0 class
      1 0 0 id

      Tag < Class < Id < inline-style < !important 
      */
    ```
  * ![xác định độ ưu tiên trong CSS đơn giản với VSCode](.\example2\selector-specificity-css.png)

# 38. Nắm vững kiến thức về child selectors

```css
ul{
  font-size: 5rem;
  font-weight: bold;
}
li:first-child{
  color: palevioletred;
}
li:last-child{
  color: #ffa500;
}
li:nth-child(2){
  color: aquamarine;
}
li:nth-child(4){
  color: bisque;
}
li:not(:first-child){
  color: green;
}
li:nth-child(odd){
  color: #ffa500;
}
```

**`NOTE:`**

```html
  <ul>
    <li class="item">
      <span>abc</span>
    </li>
    <li class="item">
      <span>abcc</span>
    </li>
  </ul>
```

```css
li span:first-child{
  color: red; /* SaI */
}
li:first-child span{
  color: #000;
}
```

# 39. Nắm vững kiến thức về type selectors

```css
li:first-of-type{
  color: #ffa500;
}
li:last-of-type{
  color: palevioletred;
}
li:nth-of-type(even){
  color: royalblue;
}
li:first-child{
  /* Thêm 1 thẻ khác <li> vào vị trí đầu tiên, thì li:first-child sẽ bị lỗi 
  để khắc phục vấn đề này thì ta sẽ sử dụng type, vì type nó sẽ check theo kiểu.
  */
  color: royalblue; /* -> ko đổi màu */
}
li:first-of-type{
  color: #ffa500;
}
```

# 40. Thành thạo `combinators` trong CSS
```html
  <!-- yêu cầu: tất cả class title nằm sau <h3> có màu chữ xanh lá -->
  <h3>Title</h3>
  <h4 class="title1">Content</h4>
  <h4 class="title1">Content</h4>
  <h4 class="title1">Content</h4>
  <h5 class="title2">Content 2</h5>
  <h5 class="title2">Content 2</h5>
  <h5 class="title2">Content 2</h5>
```

```css
h3 + .title1{
  color: green; /*-> chỉ có .title1 liền kề mới đc chuyển màu xanh */
}
/* h3 +.title1 + .title2{
  color: #ffa500;
} */

h3 ~.title2{
  /* đứng cùng cấp với nhau nhưng ko nhất thiết phải liền kề */
  color: #ffa500; /*-> tắt cả .title2 đều đc chuyển màu cam */
}
/* Dùng nhiều khi đi làm */
```

# 41. Tìm hiểu thêm các selectors nâng cao

**[https://www.w3schools.com/cssref/css_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp)**
```html
  <!-- yêu cầu: chọn ra các thẻ a có href bắt đầu bằng https -> sử dụng selector nâng cao  -->
  <a href="https://google.com">google.com</a>
  <a href="google.vn">google.vn</a>
  <a href="www.demo.com">demo.com</a>
  <a href="xyz.abc">xyz.abc</a>

  <!-- chọn ra những cái div có data-title chính xác = value -->
  <div data-title="value">VALUE</div>

  <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum, voluptatem consequuntur! Repellendus voluptatem excepturi ut eaque labore est vel sint, animi blanditiis, pariatur fuga eos laudantium nam debitis cumque inventore?</p>

```
```css
a[href^="https"]{
  /* dấu mũ ^ -> chọn ra các thẻ a có href bắt đầu bằng https */
  color: #000;
} 
a[href$=".vn"]{
  /* dấu $ -> chọn ra các thẻ a có href kết thúc bằng vn  */
  color: #00aefd;
}
a[href*="www"]{
  /* dấu * -> chọn ra các thẻ a có href có chứa www  */
  color: violet;
}
div[data-title="value"]{
  /* chọn ra những cái div có data-title chính xác = value*/
  color: red;
}
p::first-letter{
  /* Lấy kí tự đầu tiên */
  color: red;
  font-size: 4rem;
}
p::first-line{
  /* lấy dòng đầu tiên */
  color: #00aefd;
}
```

# 42. Nắm vững thuộc tính transition cơ bản

```css
.boxed2{
  width: 20rem;
  height: 20rem;
  background-color: aquamarine;
  /* transition: property timer(s) easing(linear(chậm đều), ease(nhanh đều)....); */
  /* transition: background-color 0.2s linear; */
  /* transition-delay: 0.2s; */
  transition: background-color 0.2s ease, color 1s ease;
  /* transition: all 0.2s linear;   */
}
.wrap:hover .boxed2{
  display: inline-block;
}
.boxed2:hover{
  background-color: royalblue;
  color: white;
  /* display: none; ko áp dụng hover, transition đc */
}

```

# 43. Bài tập chương 3

1. Tạo ra 6 buttons với kiến thức đã học, và có gradient đẹp như hình, có thể sử dụng BEM như `btn btn--green` chẳng hạn, trong các buttons này đều có `box-shadow` tương ứng với màu gradient luôn nên chú ý nhé: 
**[gradient-Buttons](.\exercise-2\gradient-btn.png)**

2. Tạo ra text gradient đơn giản như hình: codropspz-tympanus.netdna-ssl.com/codrops/wp-content/uploads/2015/02/TextFill_image6.png

3. Sử dụng CSS về `child` hoặc `type` để làm các màu như hình ví dụ `color__item:first-child{background-color:red}`: 
**[colors](.\exercise-2\color.webp)**

4. Sử dụng :hover để khi hover vào các màu ở các bài 3 thì đổi màu bât kỳ mà các bạn thích, lưu ý có `transition` cho nó mượt

5. Cho HTML như sau

```html
<div data-link="https.//google.com">google.com</div>

<div data-link="vnexpress.vn">facebook.com</div>

<div data-name="hello">hello</div>

<div data-name="againhello">again hello</div>

<input type="email" name="email">

<input type="text" name="fullname">

```

- Dùng kiến thức về Selectors để chọn ra các thẻ `div` có `data-link` bắt đầu bằng https

- Chọn ra các thẻ `div` có `data-link` kết thúc bằng `.vn`

- Chọn ra các thẻ `div` có `data-name` có chứa chữ `hello`

- Chọn ra `input` có `type` là email

- Chọn ra `input` có `name` là fullname

## **[mySolution](.\exercises-2)**

### *Chương 4: Kiến thức CSS nâng cao*

