#### [Exbook: Sass and compass for designer. (Tiếng việt)](https://github.com/ngnam/learn-sass-and-compass-for-designer) 
*Bạn có thể tải sách gốc tại đây nếu muốn xem với ngôn ngữ tiếng anh [Tải sách tại đây!](https://github.com/ngnam/learn-sass-and-compass-for-designer/blob/master/books/SassandCompassforDesigners.pdf).*

*[Tham khảo http://sassandcompass.com](http://sassandcompass.com/)*

*Đôi điều tâm sự*

> *"Bạn có thể bất cứ điều gì, chỉ cần bạn có một lòng quyết tâm và không sợ những khó khắn, cho dù bạn là ai, bạn đang làm gì, bạn đang sống ở đâu"*

> *"Sống ở đời không nhất thiết là phải sống được ít nhất 30 năm, mà là bạn đã cống hiến được gì cho xã hội."*

#### # Mục đích tôi dịch cuốn sách này:

1. Giúp tôi học sass để có thể viết css nhanh hơn.
1. Tôi là một font-end developer web designers.
1. Tạo ra nguồn tài liệu để các bạn sau này có thể học hỏi.
1. Tôi tin rẳng cuốn sách này sẽ giúp bạn cải thiện đàng kể kỹ năng css của bạn.

#### # Đôi điều về cuốn sách này:

 > "I wish I’d had this book when I was learning Sass."

![](/images/learn-sass.png)

* Cuốn sách này chỉ dành cho web designers chứ không dành cho lập trình viên. 
* Đọc cuốn sách này sẽ giúp bạn làm thế nào viết css dễ dàng, dễ bảo trì hơn với các tiền xử lý css và sử dụng nền tảng compass.
* Để đọc được cuốn sách này, điều cần biết chỉ là css và html.

----

#### # Nội dung cuốn sách gồm: 
##### # Chương 1 - Làm quen với sass và compass
* Trong chương này bạn sẽ tìm hiểu về nguồn gốc xuất xứ sass và compass. Cách thức bảo trì và tổng quan những khái niệm quan trọng, những gì khác biệt giữa chúng. Hy vọng sau chương này bạn sẽ có cái nhìn khả quan hơn về sass và compass.
* Tổng quan về các tính năng như: nesting, @extend, mixins và colour manipulations 
* Cài đặt chúng trên hệ thống của bạn.

###### // *Nesting trong sass:* 
    p {
        color: red;
        a {
          color: green;
          }
      }

###### // *@extend :*
    .first-rule { 
        color: red; 
    }
    a { 
        @extend .first-rule; 
        width: 100%; 
      }

###### // Mixin
`@include clearfix;`

###### // color manipulation
`.goodbye-color-picker { color: lighten(red, 20%); }`

**Hỗ trợ cả tùy chọn, giao diện đồ họa và giao diện dòng lệnh. nếu như bạn cảm thấy giao diện dòng lệnh không quen thuộc bạn có thể sử dụng công cụ: [codekit](http://incident57.com/codekit/), [livereload](http://livereload.com/) hoặc [scout-app](http://mhs.github.io/scout-app/)**

##### # Chương 2 - Xây dựng một dự án với sass và compass

> *Trong Chương 2 của cuốn sách 'Sass and Compass for Designers' bạn sẽ tìm hiểu tất cả các yếu tố cơ bản cần thiết để tạo ra một nền tảng vững chắc cho tất cả các dự án có sử dung Sass và Compass trong tương lai.*

###### # Bạn sẽ học được:

* Làm thế nào để cấu hình các dự án Compass và sửa đổi các tập tin cấu hình Compass
*  Làm thế nào để thay đổi định dạng của CSS mà Sass tạo
* Các kiểu comment khác nhau có sẵn trong Sass
* Làm thế nào để tạo ra và sử dụng các biến
* Làm thế nào để tạo ra một base' Sass và Compass dự án tùy chỉnh có thể được sử dụng như là một điểm khởi đầu cho các dự án trong tương lai.

###### # Học cách sử dụng biến
`$i-am-a-variable: red;`

###### # Sử dụng các kiểu comment
    // Like this
    /* And like this */
    /*! And LOUD comments like this */

###### # Tùy chỉnh file cấu hình config.rb
    http_path = "/"
    css_dir = "css"
    sass_dir = "sass"
    images_dir = "img"
    javascripts_dir = "js"
    fonts_dir = "css/fonts"

###### # Import file
`@import "partials/header";`

###### # Tùy chỉnh tạo mới project
`compass create --sass-dir "sass" --css-dir "css" --javascripts-dir "js" --images-dir "img"`

##### # Chương 3: Hiểu quy tắc xếp chống, Mở rộng, Thay thế, and Mixins

###### # Quy tắc xếp chồng
     .button {
        height: 25px;
        .touch & {
           height: 44px;
        }
     }

###### # Quy tắc mở rộng
     first-selector {
        // I do things
     }
     .second-selector {
        @extend .first-selector;
        // I now do the first selector things too
        // Plus any additional things...
     }

###### # Thay thế selector
    // Box
    %box {
        padding: 2em;
        color: $color10;
        background-color: $color11;
    }
    // Warning Box
    .warning-box {
        @extend %box;
        border: 2px dotted $color1;
    }
    // Success Box
    .success-box {
       @extend %box;
       border: 2px dotted $color4;
    }

###### # Học viết và sử dụng @mixin
    @mixin bs($bs-type: border-box) {
       -webkit-box-sizing: $bs-type;
       -moz-box-sizing: $bs-type;
       box-sizing: $bs-type;
    }

##### # Chương 4 - Thao tác màu sắc một cách dễ dàng.

###### # trộn màu
    .item {
         color: tint($existing-color, 10%);
    }

###### # Trong chương này bạn sẽ học được

* Làm thế nào để dễ dàng thực hiện chuyển đổi từ hex để RGBA
* Điều chỉnh màu sắc, độ sáng và độ đậm
* Làm sáng và làm tối màu
* Làm thế nào để làm cho màu sắc trong suốt
* Trộn các màu với nhau

Tôi tin tưởng, một khi bạn nắm vững các kỹ thuật màu Sass và Compass, bạn sẽ không bao giờ mở một bảng chọn màu sắc một lần nữa.

###### # Khử bão hòa
`a { background-color: desaturate($color1, 80%);}`

###### # Thay đổi độ trong suốt
`a { background-color: transparentize($color1, .5);}`

###### # Chuyển đổi sang mã màu RGBA
    a {
       background-color: rgba(red,.9);
    }

##### # Chương 5 - Responsive and Flexible Grids

##### # Chương 6 - Advanced Media Queries

##### # Chương 7 - Easy CSS3, Image Sprites, and More with Compass.
##### # Chương 8 - Programmatic Logic with Sass.

##### # Chương 9 - Becoming a Sass and Compass Power User.

----
> Xem Từng chương tại đây:
###### [# Chương 1 - Bắt đầu với sass](https://github.com/ngnam/learn-sass-and-compass-for-designer/blob/master/Chapter1.md)
###### [# Chương 2 - Cài đặt Sass và compass trong Projects ](https://github.com/ngnam/learn-sass-and-compass-for-designer/blob/master/Chapter-2-Setting-Up-a-Sass-and-Compass-project.md)
###### [# Chương 3 - Làm quen với Nesting, Extend, Placeholders, and Mixins](https://github.com/ngnam/learn-sass-and-compass-for-designer/blob/master/Chapter-3-Lam-quen-voi-Nesting-Extend-Placeholders-and-Mixins.md)

##### Đang dịch ... 

**Cảm ơn bạn đã quan tâm!**