### _Chương 5: Flexbox toàn tập_

# 61. Flexbox là gì ? Giới thiệu về Flexbox

```css
/* Flexbox là 1 giá trị trong display: flex, đi kèm với flex thì còn có rất nhiều thuộc tính đi kèm nữa để dàn layout. 
*/
```

# 62. Flexbox toàn tập #1

```html
<ul class="list">
  <li class="list_item">a</li>
  <li class="list_item">
    Lorem ipsum dolor sit amet consectetur adipisicing elit.
  </li>
  <li class="list_item">c</li>
</ul>
```

```css
/* khi sử dụng flex -> những phần bị ảnh hưởng là con của nó */

.list {
  margin-top: 1rem;
  display: flex;
  flex-direction: row; /* mặc định là row(ngang), */
  align-items: stretch;
  align-items: flex-start;
  align-items: baseline;
  /* mặc định là stretch -> các cột tự động cao bằng nhau */
  /* flex-start -> căn trên đầu */
  /* flex-end -> căn ở dưới */
  /* center -> căn giữa */
  /* baseline -> căn đuôi chữ của thằng đầu tiên */
  /* yêu cầu: chỉ thằng cuối cùng nó nằm phía dưới -> align-self: chỉ áp dụng cho phần tử con */
  justify-content: flex-start;
  justify-content: space-between;
  justify-content: space-around;
  justify-content: space-evenly;
  /* mặc định là flex-start -> các phần tử con nằm bên trái */
  /* flex-end -> phải */
  /* center -> giữa */
  /* space-between -> 3 cái 1 đầu 1 giữa 1 đầu còn lại */
  /* space-around -> khoảng trống 2 bên bằng 1/2 khoảng trống giữa */
  /* space-evenly -> khoảng trống luôn đều nhau */
  flex-wrap: nowrap;
  flex-wrap: wrap;
  /* ko bị rớt hàng do măc định flex-wrap: nowrap */
  flex-flow: row nowrap;
  /* viết tắt của flex-direction: & flex-wrap */
}
.list_item {
  background-color: orange;
  padding: 1rem;
  margin: 5px;
  width: 40%;
}
.list_item:first-child {
  font-size: 5rem;
}
.list_item:last-child {
  align-self: flex-end;
}
```

# 63. Flexbox toàn tập #2

```css
.list {
  flex-direction: column;

  align-items: stretch;
  align-items: flex-start;
  align-items: center;
  align-items: flex-end;
  align-items: baseline;

  justify-content: flex-start;
  height: 50rem;
  justify-content: center;
  /*xét theo chiều cao bao ngoài */
  justify-content: space-between;
  justify-content: space-around;
  justify-content: space-evenly;

  align-items: stretch;
}
.list_item:nth-child(2) {
  align-self: center;
}
.list_item:last-child {
  align-self: flex-end;
}
```

# 64. Flexbox toàn tập #3

```css
.list {
  flex-direction: column;
  /* -> dcba */
  /* yêu cấu: đảo lại thành abdc -> order cho phần tử con*/
}
.list_item {
  order: 0;
}
.list_item:nth-child(2) {
  order: 1;
}
.list_item:nth-child(3) {
  order: 4;
}
.list_item:last-child {
  order: 2;
}
```

```html
<!-- CENTERING by FLEXBOX -->
<div class="icon">
  <i class="fa fa-user"></i>
</div>
```

```css
.icon {
  width: 10rem;
  height: 10rem;
  border-radius: 1rem;
  background-color: royalblue;
  color: #fff;
  /* centering by flexbox */
  display: flex;
  align-items: center;
  justify-content: center;
  /* 
  position: relative
  
  > position: absolute;
  top50%
  left50%
  transform:translate(-50%;-50%);
  */
}
```

```html
<!-- CHIA LAYOUT -->
<div class="layout">
  <div class="icon">
    <i class="fa fa-user"></i>
  </div>
  <p>
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nulla expedita
    quod ea ducimus quia ullam eaque amet vel voluptatibus? Perspiciatis, libero
    magnam. Amet aspernatur, sed repellendus eum atque maiores unde.
  </p>
</div>
```

```css
.layout {
  display: flex;
  /* ERROR: icon bị bóp mặc dù đã xét w h
  -> hàm calc */
}
.icon {
  width: 10rem;
  height: 10rem;
  border-radius: 1rem;
  background-color: royalblue;
  color: #fff;
  /* centering by flexbox */
  display: flex;
  align-items: center;
  justify-content: center;
}
.layout p {
  /* width: calc(100% - 10rem); */
  --value: 10rem;
  width: calc(100% - var(--value));
  /* margin-bottom: -100px; */
  margin-bottom: calc(-1 * 100px);
}
```

# 65. Các thủ thuật chia layout hay mà bạn nên biết khi dùng flexbox

```html
<ul class="image_list">
  <li class="image_item">
    <img
      src="https://images.unsplash.com/photo-1593642632823-8f785ba67e45?ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=889&q=80"
      alt="item"
      class="image"
    />
  </li>
  <li class="image_item">
    <img
      src="https://images.unsplash.com/photo-1627266428462-c808247437e7?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=334&q=80"
      alt="item"
      class="image"
    />
  </li>
  <li class="image_item">
    <img
      src="https://images.unsplash.com/photo-1627139873347-ad423058eae0?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=401&q=80"
      alt="item"
      class="image"
    />
  </li>
  <li class="image_item">
    <img
      src="https://images.unsplash.com/photo-1627244714766-94dab62ed964?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=401&q=80"
      alt="item"
      class="image"
    />
  </li>
  <li class="image_item">
    <img
      src="https://images.unsplash.com/photo-1627244714766-94dab62ed964?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=401&q=80"
      alt="item"
      class="image"
    />
  </li>
</ul>
```

```css
:root {
  --spacing: 1rem;
}
.image_list {
  display: flex;
  /* justify-content: space-between; 
  -> ERROR: khi có nhiều ảnh thì sẽ ko ra đc layout như ý muốn
  */
  flex-wrap: wrap;
  margin: 5rem 0 0 calc(-1 * var(--spacing));
  /* nên dùng cách margin âm -> mọi trường hợp */
}
.image_item {
  width: calc((100% / 3) - var(--spacing));
  margin-left: var(--spacing);
  margin-bottom: var(--spacing);
  border-radius: 4px;
  overflow: hidden;
}
.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

# 66. Cách vẽ tam giác bằng CSS và cách nó hoạt động

### [https://css-tricks.com/](https://css-tricks.com/)

```html
<div class="boxed"></div>
```

```css
.boxed {
  /* width: 5rem; */
  /* height: 5rem; */
  display: inline-block;
  /* background-color: #000; */
  margin: 2rem auto;
  /* border-top: 10px solid orange;
  border-right: 10px sid red;
  border-bottom: 10px solid royalblue;
  border-left: 10px solid green; */
  /* below below */
  border-left: 10px solid transparent;
  border-right: 10px solid transparent;
  border-bottom: 10px solid orange;
  /* left triangle */
  border-top: 10px solid transparent;
  border-left: 10px solid orange;
  border-bottom: 10px solid transparent;
  /* right triangle */
  border-top: 10px solid transparent;
  border-right: 10px solid orange;
  border-bottom: 10px solid transparent;
  /* top triangle */
  border-top: 10px solid orange;
  border-right: 10px solid transparent;
  border-left: 10px solid transparent;
}
```

# 67. Sass là gì ? Giới thiệu và cài đặt

## _-> code CSS đc nhanh hơn, tối ưu hơn_

# 68. Tìm hiểu và nắm cơ bản kiến thức về Sass cho người mới

```html
<p>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quo eveniet, quidem
  atque dicta iure unde beatae magni libero recusandae, perspiciatis quibusdam
  odio, excepturi ad esse a similique harum neque saepe.
</p>
<header class="header">
  <div class="header-top">
    <div class="header-top-text">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita odio eum
      modi tempora in doloribus atque quas ab obcaecati laborum. Facere ad culpa
      modi, aliquam magni saepe dicta eaque sit?
    </div>
    <div class="header-content">
      Lorem ipsum dolor sit amet consectetur adipisicing elit
    </div>
  </div>
</header>

<div class="boxed"></div>

<div class="container">
  <div class="boxing"></div>
</div>
```

```scss
// Variables $
// Nested Mixin
// Conditional
// ------------------------------------  ------------------------------------
// * Variables $
$primary-color: #ffa400;
p {
  color: $primary-color;
}
// ** Nested code -> Lồng vào nhau, nối với nhau
/*CSS
.header{}
.header-top{}
.header-content{}
.header-content:hover{}
.header-content:before{}
.header-content:hover:before{}
*/
// SCSS
.header {
  &-top {
    color: red;
    &:hover {
      color: orange;
    }
  }
  &-content {
    font-size: 3rem;
  }
}
// ** Mixin -> một đoạn code sử dụng đi sử dụng lại vào mục đích nào đó ~ hàm
@mixin size($width, $height: $width) {
  width: $width;
  height: $height;
}
@mixin bg($color: #000) {
  background-color: $color;
}
.boxed {
  // width: 10rem;
  // height: 10rem;
  @include size(10rem, 20rem);
  // background-color: #ffa400;
  @include bg(#ff6651);
}
// *** Conditional
@mixin absCenter($direction: "left") {
  position: absolute;
  @if $direction == "both" {
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
  @if $direction == "left" {
    left: 50%;
    transform: translateX(-50%);
  }
  @if $direction == "top" {
    top: 50%;
    transform: translateY(-50%);
  }
}
.container {
  width: 100%;
  height: 40rem;
  background-color: royalblue;
  position: relative;
  .boxing {
    @include size(10rem);
    background-color: #ffa400;
    @include absCenter("both");
  }
}
```

# 69. Các lỗi hay gặp khi cài đặt Sass và cách khắc phục

# 70-71-72. Thực hành code giao diện Dropdown

# 73-74-75. Thực hành code giao diện đơn giản với flexbox

# 76. Responsive là gì ? Giới thiệu về Responsive toàn tập

- Responsive: làm cho web hiển thị trên các thiết bị khác nhau, trên các trình duyệt khác nhau và luôn luôn đẹp, vẫn đáp ứng về UI(User Interface - Giao diện ng dùng) & UX(User Experience - trải nghiệm ng dùng).

- Hiện nay ng dùng điện thoại rất nhiều nên 1 website có responsive là nên làm

- Mobile First & Desktop First

```css
/*BREAK POINT: 320 480 768 1024 1280 1366 1440 1600 1920*/
/* Mobile First: min-width >= 1024px */
@media screen and (min-width: 1024px) {
}
/* Desktop First: max-width: <= 1023
 (max-width = 1024 - 1 = 1023) */
@media screen and (max-width: 1023px) {
}
```

# 77-78-79. Thực hành code giao diện đơn giản sử dụng responsive

# 80. Tìm hiểu thêm các thuộc tính khác của flexbox

# 81-82-83-84. Thực hành code giao diện nâng cao

### _Chương 6: Các thẻ HTML về Form, Table_
