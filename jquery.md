# **jQuery** #

- jQuery là một thư viện của JS
- Giúp việc lập trình JS đơn giản và ngắn gọn hơn
- Dễ dàng học hơn

## **Để thêm jQuery vào trang web** ##

- Download the jQuery library from jQuery.com
- Include jQuery from a CDN, like Google

```html
<head>
<script src="jquery-3.6.1.min.js"></script>
</head>
----------------------------------------------------------------
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.1/jquery.min.js"></script>
</head>
```

## **Syntax** ##

```js
Basic syntax is: $(selector).action()
----------------------------------------------------------------
Exaample:
$(document).ready(function(){
  $("button").click(function(){
    $("#test").hide();
  });
});
```

- $ : cú pháp để truy cập jQuery
- selector : Cú pháp tìm kiếm element
- action : Các hoạt động thực hiện trên phần tử

## **The Document Ready Event**

- Tất cả các event diễn ra đều nằm trong hàm nay.

```javascript
$(document).ready(function(){

  // jQuery methods go here...

});
----------------------------------------------------------------
$(function(){

  // jQuery methods go here...

});
```

- Điều này ngăn code run trước khi document được load xong.

## **jQuery Effects - Hide and Show(Các hiệu ứng)** ##

```js
$("#hide").click(function(){
  $("p").hide();
});

$("#show").click(function(){
  $("p").show();
------------------------------------------------------------------------
$(selector).hide(speed,callback);

$(selector).show(speed,callback);
});
------------------------------------------------------------------------
jQuery toggle()

- Một phương thức giữa hide và show có thể dùng cùng 1 lúc

$("button").click(function(){
  $("p").toggle();
------------------------------------------------------------------------
$(selector).toggle(speed,callback);
});
```

## **jQuery Effects - Fade(Các hiệu ứng làm mờ hiện ra và mất đi một cách dần dần)** ##

- [Tài liệu tham khảo](https://www.w3schools.com/jquery/jquery_fade.asp)

```js
$(selector).fadeIn(speed,callback);
- fadeIn()
- fadeOut()
- fadeToggle()
- fadeTo()
```

## **jQuery Effects - Slide(Các hiệu ứng làm hiện ra slide)** ##

- [Tài liệu tham khảo](https://www.w3schools.com/jquery/jquery_slide.asp)

## **jQuery Effects - Animations(Các hiệu ứng làm animations)** ##

- [Tài liệu tham khảo](https://www.w3schools.com/jquery/jquery_animate.asp)

```js
$(selector).animate({params},speed,callback);
------------------------------------------------------------------------
$("button").click(function(){
  $("div").animate({
    left: '250px',
    height: '+=150px',
    width: '+=150px'
  });
}); 
------------------------------------------------------------------------
$("button").click(function(){
  var div = $("div");
  div.animate({left: '100px'}, "slow");
  div.animate({fontSize: '3em'}, "slow");
}); 
```

## **jQuery Effects - Stop Animations(Hiệu ứng dừng chuyển động)** ##

- [Tài liệu tham khảo](https://www.w3schools.com/jquery/jquery_stop.asp)

## **jQuery HTMLL** ##

### **Get Content - text(), html(), and val()** ###

- `text()` - Sets or returns the text content of selected elements
- `html()` - Sets or returns the content of selected elements (including HTML markup)
- `val()` - Sets or returns the value of form fields

```js
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});//Text: This is some bold text in a paragraph.
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});//HTML: This is some <b>bold</b> text in a paragraph.
```

### **Get Attributes - attr()** ###

```js
$("button").click(function(){
  alert($("#w3s").attr("href"));
});
```

### **Set Content - text(), html(), and val()** ###

```js
text() - Sets or returns the text content of selected elements
html() - Sets or returns the content of selected elements (including HTML markup)
val() - Sets or returns the value of form fields
------------------------------------------------------------------------
$("#btn1").click(function(){
  $("#test1").text("Hello world!");
});
$("#btn2").click(function(){
  $("#test2").html("<b>Hello world!</b>");
});
$("#btn3").click(function(){
  $("#test3").val("Dolly Duck");
});
```

### **A Callback Function for attr()** ###

```js
$("button").click(function(){
  $("#w3s").attr("href", function(i, origValue){
    return origValue + "/jquery/";
  });
});
```

### **Add New HTML Content** ###

- `append()` - Inserts content at the end of the selected elements
- `prepend()` - Inserts content at the beginning of the selected elements
- `after()`- Inserts content after the selected elements
- `before()`- Inserts content before the selected elements

- **Tạo một thẻ trong html**

```js
var txt2 = $("<p></p>").text("Text.");   // Create with jQuery
```

## **jQuery Traversing** ##

### **Traversing Up the DOM Tree** ###

```js
parent() : Trả về phần tử cha đầu tiên được chọn 
parents() : Trả về tất cả phần tử tổ tiên được chọn 
-------------------------------------------------------------------
Example: Trả về phần tử ul là tổ tiên của span
$(document).ready(function(){
  $("span").parents("ul");
});
-------------------------------------------------------------------

parentsUntil() : Trả về phần tử tổ tiên giữa 2 phần tử
Example:
$(document).ready(function(){
  $("span").parentsUntil("div");
});
-------------------------------------------------------------------
children() : method returns all direct children of the selected element
find() : method returns descendant elements of the selected element, all the way down to the last descendant.
```

### **Traversing Sideways in The DOM Tree** ###

```js
siblings() : Trả về tất cả phần tử là anh chị em
next() : Trả về phần tử anh em tiếp theo
nextAll() : Trả về tất cả phần tử anh em tiếp theo
nextUntil() : Trả về tất cả phần tử anh em giữa 2 phần tử
prev() : Ngược lại vs next là trước đó
prevAll() : Ngược lại vs nextAll
prevUntil() : Ngược lại với nextUntil
```

### **jQuery Traversing - Filtering** ###

- `first()`,`last()` and `eq()`, `filter()` and `not()`

## **jQuery Ajax** ##

[**TÀI LIỆU THAM KHẢO**](https://www.w3schools.com/jquery/jquery_ref_ajax.asp)

## **JS Browser BOM** ##

[**TÀI LIỀU THAM KHẢO**](https://www.w3schools.com/js/js_window.asp)

## **Web APIs - Introduction** ##

[**TÀI LIỀU THAM KHẢO**](https://www.w3schools.com/js/js_api_intro.asp)

## **JS AJAX (Asynchronous JavaScript And XML)** ##

- Đọc dữ liệu từ máy chủ web - sau khi trang đã được tải
- Cập nhật trang web mà không cần tải lại trang
- Gửi dữ liệu đến máy chủ web - ở chế độ nền

![](https://www.w3schools.com/js/pic_ajax.gif)

### **AJAX - The XMLHttpRequest Object** ###

[**TÀI LIỀU THAM KHẢO**](https://www.w3schools.com/js/js_ajax_http.asp)

## **JS JSON** ##

### **JSON.parse() (Chuyển json sang đối tượng trong JS)** ###

```js
const obj = JSON.parse('{"name":"John", "age":30, "city":"New York"}');
```

### **JSON.stringify() (Chuyển đối tượng trong JS sang JSon)** ###

```js
const obj = {name: "John", age: 30, city: "New York"};
const myJSON = JSON.stringify(obj);
```
