## *Chương 4: Kiến thức CSS nâng cao*

# 44. Thuộc tính transform để làm gì ? Tìm hiểu các giá trị hay dùng của transform
```css
.boxed{
  width: 10rem;
  height: 5rem;
  margin: 50px auto;
  background-color: red;
  transform: scale(0.5, 0.5);
  /* transform: rotate(45deg); */
  /* transform: translateX(10px); */
  /* transform: translateX(100%); 100% = 100% kích thước phần tử */
  /* transform: scale(2) rotate(45deg) translate(100%, 50%); */
  /* transform: skewX(30deg) skewY(30deg); */
  /* transform: rotateZ(30deg); */
}
/*------ tăng chiều cao nhưng ko muốn đẩy đoạn chữ xuống */
/* Transform -> thay đổi vật thể nhưng nó vẫn chiếm diện tích như cũ */
/* transform: scale(x,y) scaleX(_) scaleY(_); */
/* transform: rotate(__deg) rotateX(_deg) rotateY(30deg) rotateZ(_deg);  */
/* transform: translate(x, y) translateX(_) translateY(_); */
/* transform: skew(_deg) skewX() skewY() */
```

# 45. Tìm hiểu thuộc tính position relative
```css
.boxed{
  position: relative;
  left: 10px;
  /* right: 50px; */
  /* nếu để cả right và left -> canh theo giá trị left */
  top: 10px;
  /* bottom: -50px; */
  /* nếu để cả top và bottom -> canh theo giá trị top */
} 
/* -->relative hoạt động giống transform, nhưng ko có scale */
```

# 46. Master thuộc tính position absolute
```css
.wrap{
  width: 100%;
  height: 50rem;
  background-color: black;
  position: relative;
}
/* 
chạy theo phần tử cha có thuộc tính position: relative hoặc absolute 
-> phần tử con khi sử dụng absolute thì sẽ chạy theo phần tử cha có relative hoặc absolute.
*/
.text{
  position: relative;
  color: white;
  z-index: 2;
}
.boxed1{
  width: 10rem;
  height: 10rem;
  background-color: royalblue;
  /* right: 100px;
  bottom: 100px; */

  /*------ Centering  */
  /* position: absolute;
  top: 50%;
  left: 50%;  
  transform: translate(-50%,-50%); */
}
/*------ cho boxed phủ hết cái khung(overlay) */
.boxed1{
  position: absolute;
  /*------ overlay all */
  /* top: 0;
  left: 0;
  width: 100%;
  height: 100%; */

  /* top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  width: auto;
  height: auto; */

  /*------ overlay chiều ngang */
  /* width: 100%;
  top: 0;
  left: 0; */

  /* width: auto;
  left: 0;
  top: 0;
  right: 0; */

  /*------ overlay chiều dọc */
  /* height: 100%;
  top: 0;
  left: 0; */
 
  height: auto;
  left: 0;
  top: 0;
  bottom: 0;

  z-index: 1;
}
/*------ z-index. chỉ hoạt động khi đi kèm position */
```

# 47. Hiểu rõ position fixed hoạt động

```css
.header{
  height: 10rem;
  background-color: royalblue;
  position: fixed; 
  /*fixed chạy theo body, ko chạy theo phần tử cha chứa nó*/
  /* -> che nội dung bên dưới -> body padding-top*/
  width: 100%;
  top: 0;
  left: 0;

  /* transform: translate(30px, 30px);  */
  /*-> ERROR, ko nên dùng transform: translate ở phần tử cha, khi phần tử con fixed */
}
body{
  padding-top: 10rem;
}
```

# 48-49-50-51. Thực hành với thuộc tính position *[mySolution](.\exercises-position)*

# 52. Hiểu và nắm tốt pseudo :before vs :after khó nhằn trong CSS
```html
<h2 class="title">Viet Tung</h2>
```

```css
/* before after -> Công dụng Mạnh mẽ */
/* bắt buộc phải có thuộc tính content */
.title::before{
  content: "Before";
}
.title::after{
  content: "After"; 
}
/* BeforeViet TungAfter */
```

# 53-54-55-56. Thực hành với pseudo before và after *[mySolution](.\exercises-before-after)*

# 57. Tại sao before và after quan trong và lưu ý khi làm với việc với thuộc tính transform
```html
<div class="boxed">ABCCC</div>
```

```css
.boxed{
  width: 10rem;
  height: 10rem;
  /* background-color: aquamarine; */
  /* transform: rotate(45deg);  */
  /* chữ cũng bị xoay theo rotate, gây ra nhiều lỗi UI khi muốn làm hình nền phức tạp
    -> tạo 1 lớp giả bằng before after */
  position: relative;
}
.boxed::before{
  content: "";
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background-color: aquamarine;
  z-index: -1;
  transform: rotate(45deg);
  /* chữ sẽ ko bị ảnh hưởng, ko bị xoay theo khối */
}
```
# 58. Animation là gì ? Tìm hiểu và nắm kiến thức về animation cơ bản
```html```

```css
/* Animation chuyển động có thể xảy ra 1 hoặc nhiều lân, lặp lại  */
/* Hiểu đc nguyên lí hđ của animation cần làm, sử dụng những cái thuộc tính về css ra sao, sử dụng những cái keyframe % from to thế nào 
-> làm ví dụ để hiểu
*/
.boxed{
  width: 5rem;
  height: 5rem;
  background-color: brown;
  /* transform: translateX(20rem); */
  animation-name: move;
  /* tên animation cần sử dụng */
  animation-duration: 2s;
  /* 2s sẽ chạy xong */
  /* animation-direction: alternate; */
  /* normal chạy qua lại  */
  animation-iteration-count: 1;
  /* số lần lặp */
  animation-timing-function: linear;
  /* ease(nhanh dần) linear(chậm dần) .... */
  animation-fill-mode: backwards;
  /* chạy xong về vị trí ban đầu -> backwards
    chạy xong ở nguyên vị trí cuối -> forwards */
  animation: move 2s forwards infinite alternate linear 5s; /* gọn*/
  animation-delay: 5s;
}
@keyframes move{ /* tên animation */
  /* from -> to */
  from{
    transform: translateX(0);
  }to{
    transform: translateX(100%);
  }
}
```

# 59-60. Thực hành với animation *[mySolution](.\exercises-animation)*


## *Chương 5: Flexbox toàn tập*

