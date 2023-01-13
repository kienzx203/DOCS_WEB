# **PHP** #

## **PHP Variables** ##

```php
<?php
$txt = "Hello world!";
$x = 5;
$y = 10.5;

echo $txt;
echo "<br>";
echo $x;
echo "<br>";
echo $y;
?>
// Output:
Hello world!
5
10.5
----------------------------------------------------------------------------
<?php
$txt = "W3Schools.com";
echo "I love " . $txt . "!";
?>
// Output:
I love W3Schools.com!
```

- Đối với biến global thì để sử dụng trong hàm ta có 2 cách như sau

```php
C1:
<?php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15
?>
C2:
<?php
$x = 5;
$y = 10;

function myTest() {
  $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
}

myTest();
echo $y; // outputs 15
?>
```

## **PHP Data Types** ##

- String
- Integer ( -2,147,483,648 and 2,147,483,647.)
- Float (floating point numbers - also called double)
- Boolean
- Array
- Object
- NULL
- Resource

`Hàm var_dump() trả về kiểu dữ liệu và giá trị`

```php
<!DOCTYPE html>
<html>
<body>

<?php  
$x = 10.365;
var_dump($x);
?>  

</body>
</html>
//output : float(10.365)
```

## **PHP Strings** ##

- Độ dài chuỗi :

```php
<?php
echo strlen("Hello world!"); // outputs 12
?>
```

- Đếm số từ trong chuỗi :

```php
<?php
echo str_word_count("Hello world!"); // outputs 2
?>
```

- Reverse chuỗi :

```php
<?php
echo strrev("Hello world!"); // outputs !dlrow olleH
?>
```

- strpos() Trả về vị trí đầu tiên tìm thấy từ trong chuỗi

```php
<?php
echo strpos("Hello world!", "world"); // outputs 6
?>
```

- Thay thế từ trong chuỗi :

```php
<?php
echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!
?>
```

## **PHP Number** ##

- Có thể cộng chuỗi với một số, chuỗi số vẫn xem là 1 numeric.

## **PHP Constant** ##

```php
define(name, value, case-insensitive)
```

- name => tên biến
- value => giá trị
- case-insensitive => nếu true không phân biệt tên biến hoa hay thường còn default là false.

## **PHP If else** ##

```php
if (condition) {
  code to be executed if this condition is true;
} elseif (condition) {
  code to be executed if first condition is false and this condition is true;
} else {
  code to be executed if all conditions are false;
}
```

## **PHP switch** ##

```php
switch (n) {
  case label1:
    code to be executed if n=label1;
    break;
  case label2:
    code to be executed if n=label2;
    break;
  case label3:
    code to be executed if n=label3;
    break;
    ...
  default:
    code to be executed if n is different from all labels;
}
```

## **PHP foreach** ##

```php
<?php
$colors = array("red", "green", "blue", "yellow");

foreach ($colors as $value) {
  echo "$value <br>";
}
?>
//output:
red
green
blue
yellow
----------------------------------------------------------
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $val) {
  echo "$x = $val<br>";
}
?>
//output
Peter = 35
Ben = 37
Joe = 43
```

## **PHP function** ##

- **Để trả về kiểu dữ liệu trong function dùng dấu "`:`":**

```php
<?php declare(strict_types=1); // strict requirement
function addNumbers(float $a, float $b) : int {
  return (int)($a + $b);
}
echo addNumbers(1.2, 5.2);
?>
//output:
6
```

## **PHP Array** ##

- Cách tạo một array :

```php
  $cas = array();
```

- Đếm độ dài array :

```php
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars);
?>
//Output:
3
```

- Sắp xếp mảng :
  - sort() - sort arrays in ascending order
  - rsort() - sort arrays in descending order
  - asort() - sort associative arrays in ascending order, according to the value
  - ksort() - sort associative arrays in ascending order, according to the key
  - arsort() - sort associative arrays in descending order, according to the value
  - krsort() - sort associative arrays in descending order, according to the key

## **PHP Global Variables** ##

- **PHP $GLOBALS** : sử dụng truy cập biến toàn cục.

```php
<?php
$x = 75;
$y = 25;
 
function addition() {
  $GLOBALS['z'] = $GLOBALS['x'] + $GLOBALS['y'];
}
 
addition();
echo $z;
?>
//output:
100
```

- **PHP $_SERVER** :

|Element/Code|Description|
| ------------ | ------------ |
|$_SERVER['PHP_SELF']|Trả về tên tệp của tập lệnh hiện đang thực thi|
|$_SERVER['GATEWAY_INTERFACE']|Trả về phiên bản Giao diện cổng chung (CGI) mà máy chủ đang sử dụng|
|$_SERVER['SERVER_ADDR']|Trả về địa chỉ IP của máy chủ lưu trữ|
|$_SERVER['SERVER_NAME']|Trả về tên của máy chủ lưu trữ (chẳng hạn như www.w3schools.com)|
|$_SERVER['SERVER_SOFTWARE']|Trả về chuỗi nhận dạng máy chủ (chẳng hạn như Apache/2.2.24)|
|$_SERVER['SERVER_PROTOCOL']|Trả về tên và bản sửa đổi của giao thức thông tin (chẳng hạn như HTTP/1.1)|
|$_SERVER['REQUEST_METHOD']|Trả về phương thức yêu cầu được sử dụng để truy cập trang (chẳng hạn như POST)|
|$_SERVER['REQUEST_TIME']|Trả về  thời gian bắt đầu yêu cầu (chẳng hạn như 1377687496)|
|$_SERVER['QUERY_STRING']|Returns the query string if the page is accessed via a query string|
|$_SERVER['HTTP_ACCEPT']|Returns the Accept header from the current request|
|$_SERVER['HTTP_ACCEPT_CHARSET']|Returns the Accept_Charset header from the current request (such as utf-8,ISO-8859-1)|
|$_SERVER['HTTP_HOST']| Returns the Host header from the current request|
|$_SERVER['HTTP_REFERER']|Trả về URL đầy đủ của trang hiện tại (không đáng tin cậy vì không phải tác nhân người dùng nào cũng hỗ trợ nó)|
|$_SERVER['HTTPS']|Tập lệnh có được truy vấn thông qua giao thức HTTP an toàn không|
|$_SERVER['REMOTE_ADDR']|Trả về địa chỉ IP từ nơi người dùng đang xem trang hiện tại|
|$_SERVER['REMOTE_HOST']|Trả về tên Máy chủ từ nơi người dùng đang xem trang hiện tại|
|$_SERVER['REMOTE_PORT']|Trả về cổng đang được sử dụng trên máy của người dùng để giao tiếp với máy chủ web|
|$_SERVER['SCRIPT_FILENAME']|Trả về tên đường dẫn tuyệt đối của tập lệnh hiện đang thực thi|
|$_SERVER['SERVER_ADMIN']|Trả về giá trị được cung cấp cho lệnh SERVER_ADMIN trong tệp cấu hình máy chủ web (nếu tập lệnh của bạn chạy trên máy chủ ảo, thì nó sẽ là giá trị được xác định cho máy chủ ảo đó) |
|$_SERVER['SERVER_PORT']|Trả về cổng trên máy chủ đang được máy chủ web sử dụng để liên lạc (chẳng hạn như 80)|
|$_SERVER['SERVER_SIGNATURE']|Returns the server version and virtual host name which are added to server-generated pages|
|$_SERVER['PATH_TRANSLATED']| Returns the file system based path to the current script|
|$_SERVER['SCRIPT_NAME']| Trả về đường dẫn của tập lệnh hiện tại|
|$_SERVER['SCRIPT_URI']| Returns the URI of the current page|

- **PHP $_REQUEST**
- **PHP $_POST**
- **PHP $_GET**

## **PHP Regular Expressions** ##

- preg_match() : Trả về 1 nếu mẫu được tìm thấy trong chuỗi và 0 nếu không.
- preg_match_all() : Trả về số lần mẫu được tìm thấy trong chuỗi, cũng có thể là 0.
- preg_replace() : Trả về một chuỗi mới trong đó các mẫu phù hợp đã được thay thế bằng một chuỗi khác.

```php
<?php
$str = "The rain in SPAIN falls mainly on the plains.";
$pattern = "/ain/i";
echo preg_match_all($pattern, $str); // Outputs 4
?>
```

## **PHP Form Handling** ##

![](./img_php/Form%20Handling.png)

## **PHP Form Validation** ##

```php
<!DOCTYPE HTML>  
<html>
<head>
<style>
.error {color: #FF0000;}
</style>
</head>
<body>  

<?php
// define variables and set to empty values
$nameErr = $emailErr = $genderErr = $websiteErr = "";
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  if (empty($_POST["name"])) {
    $nameErr = "Name is required";
  } else {
    $name = test_input($_POST["name"]);
    // check if name only contains letters and whitespace
    if (!preg_match("/^[a-zA-Z-' ]*$/",$name)) {
      $nameErr = "Only letters and white space allowed";
    }
  }
  
  if (empty($_POST["email"])) {
    $emailErr = "Email is required";
  } else {
    $email = test_input($_POST["email"]);
    // check if e-mail address is well-formed
    if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
      $emailErr = "Invalid email format";
    }
  }
    
  if (empty($_POST["website"])) {
    $website = "";
  } else {
    $website = test_input($_POST["website"]);
    // check if URL address syntax is valid
    if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
      $websiteErr = "Invalid URL";
    }    
  }

  if (empty($_POST["comment"])) {
    $comment = "";
  } else {
    $comment = test_input($_POST["comment"]);
  }

  if (empty($_POST["gender"])) {
    $genderErr = "Gender is required";
  } else {
    $gender = test_input($_POST["gender"]);
  }
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>

<h2>PHP Form Validation Example</h2>
<p><span class="error">* required field</span></p>
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">  
  Name: <input type="text" name="name">
  <span class="error">* <?php echo $nameErr;?></span>
  <br><br>
  E-mail: <input type="text" name="email">
  <span class="error">* <?php echo $emailErr;?></span>
  <br><br>
  Website: <input type="text" name="website">
  <span class="error"><?php echo $websiteErr;?></span>
  <br><br>
  Comment: <textarea name="comment" rows="5" cols="40"></textarea>
  <br><br>
  Gender:
  <input type="radio" name="gender" value="female">Female
  <input type="radio" name="gender" value="male">Male
  <input type="radio" name="gender" value="other">Other
  <span class="error">* <?php echo $genderErr;?></span>
  <br><br>
  <input type="submit" name="submit" value="Submit">  
</form>

<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>

</body>
</html>
```

## **PHP Include Files** ##

- `require` : sẽ tạo ra lỗi nghiêm trọng (E_COMPILE_ERROR) và dừng tập lệnh.
- `includde` : sẽ chỉ đưa ra cảnh báo (E_WARNING) và tập lệnh sẽ tiếp tục.

## **PHP File Upload** ##

```html
<!DOCTYPE html>
<html>
<body>

<form action="upload.php" method="post" enctype="multipart/form-data">
  Select image to upload:
  <input type="file" name="fileToUpload" id="fileToUpload">
  <input type="submit" value="Upload Image" name="submit">
</form>

</body>
</html>
```

```php
<?php
$target_dir = "uploads/";
$target_file = $target_dir . basename($_FILES["fileToUpload"]["name"]);
$uploadOk = 1;
$imageFileType = strtolower(pathinfo($target_file,PATHINFO_EXTENSION));

// Check if image file is a actual image or fake image
if(isset($_POST["submit"])) {
  $check = getimagesize($_FILES["fileToUpload"]["tmp_name"]);
  if($check !== false) {
    echo "File is an image - " . $check["mime"] . ".";
    $uploadOk = 1;
  } else {
    echo "File is not an image.";
    $uploadOk = 0;
  }
}

// Check if file already exists
if (file_exists($target_file)) {
  echo "Sorry, file already exists.";
  $uploadOk = 0;
}

// Check file size
if ($_FILES["fileToUpload"]["size"] > 500000) {
  echo "Sorry, your file is too large.";
  $uploadOk = 0;
}

// Allow certain file formats
if($imageFileType != "jpg" && $imageFileType != "png" && $imageFileType != "jpeg"
&& $imageFileType != "gif" ) {
  echo "Sorry, only JPG, JPEG, PNG & GIF files are allowed.";
  $uploadOk = 0;
}

// Check if $uploadOk is set to 0 by an error
if ($uploadOk == 0) {
  echo "Sorry, your file was not uploaded.";
// if everything is ok, try to upload file
} else {
  if (move_uploaded_file($_FILES["fileToUpload"]["tmp_name"], $target_file)) {
    echo "The file ". htmlspecialchars( basename( $_FILES["fileToUpload"]["name"])). " has been uploaded.";
  } else {
    echo "Sorry, there was an error uploading your file.";
  }
}
?>
```

## **PHP Cookie** ##

- **Create Cookies With PHP**
  - setcookie(name, value, expire, path, domain, secure, httponly);

## **PHP Session** ##

- [Tài liệu tham khảo](https://www.w3schools.com/php/php_sessions.asp)

## **PHP Filters** ##

- [Tài liệu tham khảo](https://www.w3schools.com/php/php_filter.asp)

## **PHP Callback Functions** ##

```php
<!DOCTYPE html>
<html>
<body>

<?php
function my_callback($item) {
  return strlen($item);
}

$strings = ["apple", "orange", "banana", "coconut"];
$lengths = array_map("my_callback", $strings);
print_r($lengths);
?>

</body>
</html>
//output:
Array
(
    [0] => 5
    [1] => 6
    [2] => 6
    [3] => 7
)
```

## **PHP and JSON** ##

- json_encode()
- json_decode()

- [Tài liệu tham khảo](https://www.w3schools.com/php/php_json.asp)

## **PHP Exceptions(Ngoại lệ)** ##

- [Tài liệu tham khảo](https://www.w3schools.com/php/php_exceptions.asp)

## **PHP OOP** ##

```php
<?php
class Fruit {
  // Properties
  public $name;
  public $color;

  // Methods
  function set_name($name) {
    $this->name = $name;
  }
  function get_name() {
    return $this->name;
  }
}

$apple = new Fruit();
$banana = new Fruit();
$apple->set_name('Apple');
$banana->set_name('Banana');

echo $apple->get_name();
echo "<br>";
echo $banana->get_name();
?>
```

- **Để kiểm tra đối tượng có thuộc lớp class hay không**

```php
<?php
$apple = new Fruit();
var_dump($apple instanceof Fruit);
?>
//output:
bool(true)
```

- ## **__constructor** ##

  - php sẽ tự động gọi hàm này sau khi một đối tượng được tạo.

```php
  <?php

class Fruit {
  public $name;
  public $color;

  function __construct($name, $color) {
    $this->name = $name;
    $this->color = $color;
  }
  function get_name() {
    return $this->name;
  }
  function get_color() {
    return $this->color;
  }
}

$apple = new Fruit("Apple", "red");
echo $apple->get_name();
echo "<br>";
echo $apple->get_color();
?>
```

- ## **__destruct** ##

  - php sẽ tự động gọi hàm xóa khi hết tập lệnh.

```php
<?php
class Fruit {
  public $name;
  public $color;

  function __construct($name) {
    $this->name = $name;
  }
  function __destruct() {
    echo "The fruit is {$this->name}.";
  }
}

$apple = new Fruit("Apple");
?>
```

- ## **__destruct (kế thừa)** ##

```php
<?php
class Fruit {
  public $name;
  public $color;
  public function __construct($name, $color) {
    $this->name = $name;
    $this->color = $color;
  }
  public function intro() {
    echo "The fruit is {$this->name} and the color is {$this->color}.";
  }
}

// Strawberry is inherited from Fruit
class Strawberry extends Fruit {
  public function message() {
    echo "Am I a fruit or a berry? ";
  }
}
$strawberry = new Strawberry("Strawberry", "red");
$strawberry->message();
$strawberry->intro();
?>
```

- ## **Abstract tính trừu tượng** ##

```php
<?php
abstract class ParentClass {
  // Abstract method with an argument
  abstract protected function prefixName($name);
}

class ChildClass extends ParentClass {
  // The child class may define optional arguments that are not in the parent's abstract method
  public function prefixName($name, $separator = ".", $greet = "Dear") {
    if ($name == "John Doe") {
      $prefix = "Mr";
    } elseif ($name == "Jane Doe") {
      $prefix = "Mrs";
    } else {
      $prefix = "";
    }
    return "{$greet} {$prefix}{$separator} {$name}";
  }
}

$class = new ChildClass;
echo $class->prefixName("John Doe");
echo "<br>";
echo $class->prefixName("Jane Doe");
?>
```

- ## **Interfaces** ##

  - [**Tài liệu tham khảo**](https://www.w3schools.com/php/php_oop_interfaces.asp)

- ## **Traits (Kế thừa nhiều lần)** ##

```php
<?php
trait message1 {
  public function msg1() {
    echo "OOP is fun! ";
  }
}

trait message2 {
  public function msg2() {
    echo "OOP reduces code duplication!";
  }
}

class Welcome {
  use message1;
}

class Welcome2 {
  use message1, message2;
}

$obj = new Welcome();
$obj->msg1();
echo "<br>";

$obj2 = new Welcome2();
$obj2->msg1();
$obj2->msg2();
?>
```
