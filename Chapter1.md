## [Exbook: sass and compass for designer. (tiếng việt)](https://github.com/ngnam/learn-sass-and-compass-for-designer)

#### [# Chương 1: Làm quen với sass, compass](https://github.com/ngnam/learn-sass-and-compass-for-designer/blob/master/Chapter1.md)

**Trong chương này bạn sẽ học đưọc**

> 1. Tại sao cần css preprocessors.
1. Tại sao nên sử dụng sass và compass.
1. Sass là gì.
1. Compass là gì.
1. Hướng dẫn cài đặt sass, compass.
1. Tại sao nên chọn một công cụ để xây dựng sass.

----

#### CSS processors
*Ai cũng biết css là một declarative, không phải là một ngôn ngữ lập trình. Hiểu đơn giản nó gồm các thuộc tính style và các giá trị được chúng ta khai báo để tạo ra các rules trong css giúp cho trình duyệt đọc được và hiển thị lên màn hình.*

*Một ngôn ngữ lập trình là một kiểu ngôn ngữ có cấu trúc logics. Trong css nó được hiểu như trong một thẻ `Form` có một thẻ `h1` nằm trong một thẻ `nav`, có màu `xanh`; một thẻ `header` có màu `đỏ`*

*Một ngôn ngữ lập trình thì được khai báo nhiều biến **Varibles**. Trong **css** nó đưọc tạo ra để thay thế nhanh chóng các giá trị như màu sắc (`color`), `border`, `px`, `width`, `height`,...*

##### Nếu như mục đích là chỉ để tạo ra css, vậy tại sao lại không viết luôn css ngay từ đầu?

Chúng ta thì dùng css mỗi ngày. Chúng ta có thể sử dụng nó để viết nên tất cả những gì giống như màn hình hiện thị mà ta muốn, xây dựng 1 website reponsive hiện thị được trên tất cả các thiết bị. **Sass và compass giúp cho việc viết css trở nên nhanh và đơn giản hơn rất nhiều.**

#### Tại sao nên sử dụng sass và compass
Chúng ta đều biết rằng có một só lượng lớn các tổ chức như **BBC**, **eBay**, và  **LinkedIn**, ... đang làm việc với nó và sử dụng nó để viết ra mã css. Nó là một chuẩn giúp cho việc trao đổi giữa các nhà phát triển trong một tổ chức. Ngay bây giờ cuốn sách này sẽ giúp bạn học những tính năng và sử dụng SASS.

***Cuối cùng Tôi rất mong cuốn sách này sẽ giúp bạn cải thiện kỹ năng css và viết css nhanh, đơn giản hơn trưóc.***

#### Sử dụng biến (variables) 
*Chỉ khai báo một giá trị cho một biến.*

Đã bao nhiêu lần, khi bạn làm việc với css trong một trang web, mà bạn cần khai báo lặp lại một giá trị màu sẳc nhiều lần? Có thể là 10 lần, 20 lần, chậm chí nhiều hơn nữa. Tuy nhiên, chúng ta có rất nhiều giá trị màu sắc, tôi thì thưòng xuyên ghi nhớ một đến ba giá trị hex để sử dụng nhanh chóng khi xây dựng 1 website. Với Sass chúng ta có thể khai báo các giá trị màu sắc đó bằng một biến. Và một biến chỉ được khai báo một giá trị mà thôi.

*Khai báo 3 biến màu sắc tưong ứng sau:*

	$red: #ff0b13;
	$blue: #091fff;
	$green: #11c909;

#### Làm quen với cú pháp trong khai báo biến

**Giống** như quy tắc đặt tên biến thông thường, tên biến gồm tiền tố '$', bắt đầu là các ký tự chữ cái, không có khoảng trống. Sau đó, tên biến được khai báo sau giá trị thuộc tính trong css. Trong ví dụ sau, biến $green sẽ khai báo màu green cho thuộc tính color.

*# code trong file .scss :*

	.Toi_muon_mau_green {
	    color: $green;
	}

*# code được sinh ra :*

	.Toi_muon_mau_green {
		color: #11c909;
	} 

----
#### Ghi nhớ: 
* Trong sass, compile giúp chuyển đổi từ định dạng sass thành css.
* Trong sass, 2 định dạng file quen thuộc là scss và sass. 
* Việc viết và nhớ các giá trị tên biến thì đơn giản và nhanh hơn việc nhớ các giá trị mã hex đó. Ngoài ra, khi ta cần thay đổi giá trị màu sắc, ta chỉ cần thay đổi tên biến mà không cần phải tìm và thay thế bằng một giá trị do các design đặt ra.

#### Giá trị màu RGBA tự động và chuyển đổi
RGBA (Red Green Blue Alpha) and HSLA (Hue Saturation Lightness Alpha) là 2 chuẩn màu đã được hỗ trợ hầu hết trên trình duyệt ngày nay. Sắp xếp theo trình duyệt cũ thì độ tương thích của các giá trị mã màu là: Hex color, sau đó là RGBA color hoặc HSLA color. Điều đó có nghĩa là với những trình duyệt mới hơn thì nên sử dụng mã RGBA\HSLA còn với những trình duyệt cũ thì nên sử dụng mã HEX.

- Nếu sử dụng các phần mềm như photoshop, fireworks, .. thi việc khai báo giá thị color bằng các mã hex thì rất đơn giản:

	.color-me-bad {
		color: #11c909;
		color: rgba(17, 201, 9, 0.9);
	}

* Với Sass điều đó thực sự đơn giản:

	.color-me-good {
		color: $green;
		color: rgba($green, 0.9);
	}

* khi complie nó sẽ sinh ra mã css:

	.color-me-bad {
		color: #11c909;
		color: rgba(17, 201, 9, 0.9);
	}

**Bây giờ chỉ cần nhớ tên biến để sử dụng sẽ đơn giản hơn rất nhiều.**

#### Forget about vendor prefixes
Tôi là một trong những người ưa thích CSS3. Trước đây tôi thưòng sử dụng hình ảnh và nhiều thứ khác để dùng trong css. Tuy nhiên, với những tình năng mới (background gradients, box-shadows, transformations, vầ nhiều tính năng khác) đã giúp tôi làm điều đó đơn giản hơn rất nhiêu.

* Bo tròn các góc cho class rounded

	.rounded {
		-webkit-border-radius: 4px;
		-moz-border-radius: 4px;
		-ms-border-radius: 4px;
		-o-border-radius: 4px;
		border-radius: 4px;
	}

* Với Sass, compass cung cấp một công cụ miễn phí 'mixins', với yêu cầu trên ta chỉ cần dòng sau:

	.rounded {
		@include border-radius(4px);
	}

**Sass, compass giúp ta tiết kiệm được thời gian xây dựng, số dòng code.**

#### Quy tắc xếp lồng
Sass cho phép các nguyên tắc được lồng trong nhau.

* Chẳng hạn như ta muốn viết css cho thẻ a ở trong thẻ nav và css hover, active cho thẻ a , ta nên viết như sau:

	nav {
		a {
			color: $red;
			&:hover {
				color: $green;
			}
			&:active {
				color: $blue;
			}
		}
	}

* css sinh ra:

	nav a {
		color: #ff0b13;
	}

	nav a:hover {
	 color: #11c909;
	}

	nav a:active {
		color: #091fff;
	}

#### Media queries the simple way
Hầu hết trang web ngày nay nên viết reponsive để có thể hoạt động tốt trên nhiều thiết bị khác nhau.

* Đoạn css sau: (font-size của thẻ h1 sẽ thay đổi cho phù hợp với từng loại màn hình khác nhau)

	@media only screen and (min-width: 280px) and (max-width: 479px) {
		.h1 {
			font-size: 1.1em;
		}
	}
	@media only screen and (min-width: 480px) and (max-width: 599px) {
		.h1 {
			font-size: 1em;
		}
	}
	@media only screen and (min-width: 600px) and (max-width: 767px) {
		.h1 {
			font-size: 0.9em;
		}
	}

* Với Sass, ta sẽ khai báo các biến với độ rộng tưong ứng với từng màn hình để hiển thị, sau đó gọi chúng ra như sau:

	h1 {
		@include MQ(XS) {
			font-size: 1.1em;
		}
		@include MQ(S) {
			font-size: 1em;
		}
		@include MQ(M) {
			font-size: 0.9em;
		}
	}

#### Làm quen với compass để complie css

Chắc bây giờ bạn đã hiểu sass là cái j rồi :D

> Sass là một siêu ngôn ngữ trên đầu trang của CSS mà được sử dụng để mô tả kiểu định dạng cho một tài liệu sạch và cấu trúc, với sức mạnh hơn CSS. Sass cung cấp một cú pháp đơn giản thanh lịch hơn cho CSS và thực thi nhiều tính năng hữu ích cho việc tạo ra các style sheet dễ quản lý.
d

*Sass thì miễn phí và không cần bản quyền*

#### Compass là gì?
Compass là một mã nguồn mở trên nền tảng CSS Authoring.
#####  Cài đặt sass và compass
##### # Cài đặt trên OS-X
- Với những người sử dụng Mac OS X, rất dễ dàng để cài đặt thông qua gói [chriseppstein/compass](https://github.com/chriseppstein/compass/downloads)

- Cài đặt sass and compass và làm việc với chúng từ **commandline**

+ Trước khi chúng ta có thể cài đặt sass và compass, ta cần cài gói **ruby** trước.

##### # Cài đặt ruby trên windows
Với những người sử dụng windows, chỉ cần tải gói 
[Ruby](http://rubyforge.org/frs/download.php/76054/rubyinstaller-1.9.3-p194.exe) về, sau đó cài đặt bình thường.

#### # Cài ruby trên linux gõ : 
	
`sudo install ruby `

#### # Cài compass:

* Trên linux\OS-X: 

	`sudo gem install compass`

* Trên windows: 

	`gem install compass`

#### # Kiểm tra phiên bản hiện tại:

	compass -v
        sass -v

#### # Kiểm tra các phiên bản sass và compass đang có trên máy chủ:

	gem list sass -a -r

	gem list compass -a -r

#### # Cài đặt phiên bản cũ hơn:

`$ sudo gem install sass`
`$ sass -v`
`$ sudo gem install sass --pre`
`$ sudo gem install compass`
`$ compass -v`
`$ sudo gem install compass --pre`

#### # Gỡ cài đặt

`$gem uninstall sass --version versionnumber`
`gem uninstall compass --version versionnumber`

### Tạo mới projects sass và  compass

`cd dir_project`
`compass create my-project`

![my-project](/images/my-project.png)

- Thư mục .sass-cache chứa các file cache sau khi buid css. không cần dùng đến nó.

- Thư mục sass: chứa các file .scss mà ta sẽ viết. Thư mục này có thể ở bất kỳ đâu trong project, nhưng tên bắt buộc phải mặc định là sass.

- Thư mục stylesheets: chứa các file css được sinh ra sau khi complie. Thư mục này cũng được để ở bất ký đâu nhưng tên bắt buộn phải mặc định là stylesheets.

- File config.rb cấu hình compass watch: 

#### # Graphical tools for working with Sass and Compass

- Scout app (http://mhs.github.com/scout-app)

- CodeKit (Công cụ này có phí :D chắc chả ai dám sài.)

