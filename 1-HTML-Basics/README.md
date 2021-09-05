# 1. Giới thiệu khoá học
# 2. Thiết lập code editor cơ bản

Các `extensions` nên cài: ✔✔✔
* Prettier
* Material Icon Theme
* Live Server
* Bracket Pair Colorizer
* Highlight Matching Tag
* SCSS Intellisence
* htmltagwrap
* HTML to CSS Autocompletion
* HTML Snippets
* Live Server Preview
* Auto Complete Tag

Các extensions hay cho `Chrome`: ✔✔✔
* Eye Dropper
* Page Ruler Redux
* VisBug

Trang web lấy ảnh miễn phí: **[https://unsplash.com/](https://unsplash.com/)**

# 3. Cấu trúc một file HTML cơ bản như thế nào?

*Web Design Ideas:* **[https://collectui.com/](https://collectui.com/)**

```html
<!DOCTYPE html> <!-- khai báo đây là kiểu văn bản HTML -->
<html lang = "en"> <!-- thuộc tính ngôn ngữ English -->
<head>
  <meta charset='utf-8'> <!-- thông báo hiển thị về ngôn ngữ -->
  <meta http-equiv='X-UA-Compatible' content='IE=edge'> 
  <title>Page Title</title> <!-- Title trang Web -->
  <meta name='viewport' content='width=device-width, initial-scale=1'> <!-- Hiển thị Responsive -->
  <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
</head>
<body>
  
  <script src='main.js'></script>
</body>
</html>
```

# 4. Các thẻ HTML cơ bản nên biết (phần 1)
# 5. Các thẻ HTML cơ bản nên biết (phần 2)

*HTML tags List:* **[https://htmlreference.io/](https://htmlreference.io/)**

Những thẻ HTML đc định nghĩa có những mục đích khác nhau.

* `<div></div>` để bọc khối, chia các khối
* `<p></p>` hiển thị đoạn văn bản dài
* Heading(tiêu đề) `<h1></h1>` ... `<h6></h6>` 
  * kiểm tra giá mặc định F12 -> tìm `user agent stylesheet`
  * SEO: trong 1 trang web thường chỉ dùng 1 thẻ `<h1></h1>` tiêu đề to cho web, thẻ `<h2></h2>` có thể đc sử dụng nhiều hơn ở các khối lớn,....
* Link `<a href="google.com" target="_blank" rel="noopener noreferrer">Google</a>`
  * `target="_blank"`: mở đường link ở Tab mới
  * `rel="noopener noreferrer"`: bảo mật, ko bị load lại trang web nếu liên kết là nặng
* Hình ảnh `<img src="_" alt="_">`
* Danh Sách 
  * `<ol><li></li></ol>` Mục lục
  * `<ul><li></li></ul>` Menu
* `<iframe src="_" frameborder="0"></iframe>` nhúng nguồn nào đó vào trang web, ytb, ins, ....
* `<strong></strong> <b></b>` in đậm
* `<em></em> <i></i>` nghiêng
* `<span></span>` văn bản ngắn
* --
* **Sematic in HTML5**, những thẻ mới trong HTML5 -> cấu trúc code gọn gàng, mạch lạc, dễ hiểu hơn
* `<header></header>` trên
* `<footer></footer>` dưới
* `<aside></aside>` trái, phải
* `<nav></nav>` Menu, điều hướng
* `<main></main>` chính
* `<section></section>` bao khối,~div
* `<article></article>` bài viết
* --
# 6. Thẻ Inline và thẻ Block khác nhau như thế nào?
* `Inline tags` vs. `Block tags`
  * **Inline tags**: thẻ có độ rộng bằng nội dung nó chứa, nằm trên 1 hàng, bị hạn chế về thuộc tính CSS, `<span></span>`...
  * **Block tags**: độ rộng bằng độ rộng thẻ chứa nó, nhiều thẻ nằm cùng cấp thì sẽ rớt xuống hàng, `<p></p>`,...
  * 2 thẻ **Inline tags**, **Block tags** hay đi chung với nhau -> Read more, Read less,...

# 7. Sự khác nhau giữa Class và Id

* `<a href="_">_</a>`
* Tùy biến attribute cho thẻ nào đó mà nó ko có
  * `<div data-href="_"></div>` -> js dùng data-href lấy dữ liệu

* `<div class="a b c" id=""></div>`
  * class: có thể trùng nhau, sử dụng cho nhiều phần tử giống nhau, nhiều class trong 1 tag
  * id: duy nhất,

# 8. BEM là gì ? Tìm hiểu về BEM toàn tập

* `BEM(Block__Element--Modifier)` là phương pháp đặt tên cho class trong HTML CSS 
    * `Block--Modifier`
    * `Block__Element`
* Laptop: Block
  * Keyboard, Mouse, Screen: Element
    * LED Keyboard, LED Mouse, fullHD Screen: Modifier
        * laptop__keyboard, laptop__mouse,
        * laptop--expensive
        * laptop__touchpad--smooth

* `BEM` ko phải là duy nhất, tùy vào cách đặt của công ty sẽ có 1 nguyên tắc đặt tên khác nhau
  * laptop__keyboard -> laptop_keyboard

# 9. Thực hành phân tích giao diện cơ bản với BEM
* FlashMessage
  * ![FlashMessage](..\course-images\daily-ui-challenge-011-large.png)
  * 
  ```html
    <!-- Ex: FlashMessage 
    Block: flash-message
    Element: image, title, description(desc), button
    Modifier: primary, secondary
  -->
  <!-- Block 1 & 2 flash-message
    flash-message_image,flash-message_title, flash-message_desc, flash-message_button
      Block 1: flash-message_title-primary, flash-message_button-primary, 
      Block 2: flash-message_title-secondary, flash-message_button-secondary
  -->
  ```

# 10. Bài tập chương 1
<!-- <details><summary><b>Đáp án</b></summary>
<p>

</p>
</details> -->

1. Liệt kê 10 thẻ inline, 10 thẻ block và các thẻ semantic HTML5 mà bạn biết

* Inline: độ rộng bằng nội dung, luôn nằm trên 1 dòng khi đc khai báo nhiều trên cùng cấp, hạn chế về CSS
  * `<span></span>`
  * `<strong></strong>`
  * `<b></b>`
  * `<i></i>`
  * `<em></em>`
  * `<a></a>`
  * `<input>`
  * `<img>`
  * `<label></label>`
  * `<title></title>`
* Block: độ rộng bằng phần chứa nó, luôn nằm rớt xuống dòng khi đc khai báo nhiều cùng cấp.
  * `<p></p>`
  * `<h_></h_>`, `sematic tags`
  * `<div></div>`
  * `<iframe></iframe>`
  * `<video></video>`
  * `<table></table>`
  * `<details></details>`
  * `<summary></summary>`
  * `<form></form>`
  * `<select></select>`
* Sematic HTML5
  * `<header></header>`
  * `<footer></footer>`
  * `<aside></aside>`
  * `<nav></nav>`
  * `<section></section>`
  * `<article></article>`
  * `<main></main>`
2. Làm 1 ví dụ về BEM cho block có tên là `boy`

`boy_arm-long`
`boy_hair`
`boy-handsome`

3. Hãy làm 1 ví dụ về sự kết hợp giữa thẻ block và thẻ inline
```html
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus imperdiet, nulla et dictum interdum, nisi lorem egestas vitae scel<span id="dots">Read more...</span></p>
```
4. Áp dụng kiến thức về BEM đặt tên cho UI này: Hint: Block có tên `dropdown`

    ![a](https://static.collectui.com/shots/1436570/dropdown-menu-large)

* Block: dropdown
* Element: dropdown_select, dropdown_option
* Modifier: dropdown_select-active

*
```html
  <div class="dropdown">
    
    <div class="dropdown_select">
      <span class="dropdown_selected"></span>
      <i class="fa fa-caret-down dropdown_caret"></i>
    </div>

    <div class="dropdown_list">
      <div class="dropdown_item">
        <span class="dropdown_title"></span>
        <i class="fa fa-flus dropdown_icon"></i>
      </div>
    </div>
      
  </div>
```

# 11. Giải bài tập chương 1
# 12. Nắm vững `Emmet` cơ bản trong VSCode

show những cái gợi ý, code nhanh hơn, thay vì copy paste

*Emmet cheat sheet* **[https://docs.emmet.io/cheat-sheet/](https://docs.emmet.io/cheat-sheet/)**

***
### [Tiếp theo: Chương 2: Kiến thức CSS cơ bản](..\2-3-CSS-Basics\README.md)
