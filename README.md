# hello-world
just another repository
 # hello-world
  just another repository
  
 +add_handle.php
  <?php
  require_once'connect.php';
  $name=$_POST['name'];
 $content=$_POST['content'];
 $price=$_POST['price'];
 echo $name;
 $sql="INSERT INTO library(name,content,price) VALUES('$name','$content',$price)";
 if(mysqli_query($con,$sql))
  {
      echo"success!";
  }
 +
 +
 +add.php
 +<html>
 +<body>
 +    <form action="add_handle.php" method="post">
 +        name：<input type="text" name="name"><br>
 +        content:<input type="text" name="content"><br>
 +        price:<input type="text" name="price"><br>
 +        <input type="submit" value="提交">
 +     </form>
 +</body>
 +</html>
 +
 +
 +config.php
 +<?php
 +	header("Content-type: text/html; charset=utf-8");
 +	define('HOST', '127.0.0.1');
 +	define('USERNAME', 'root');
 +	define('PASSWORD', '');
 +?>
 +
 +
 +connect.php
 +<?php
 +	require_once('config.php');
 +	//锟斤拷锟斤拷
 +	if(!($con = mysqli_connect(HOST, USERNAME, PASSWORD,"test"))){
 +		echo mysqli_error();
 +	}
 +	//选锟斤拷
 +	if(!mysqli_select_db($con,'test')){
 +		echo mysqli_error();
 +	}
 +	//锟街凤拷锟斤拷
 +	if(!mysqli_query($con,'set names utf8')){
 +		echo mysqli_error();
 +	}
 +?>
 +
 +
 +delete.php
 +<?php
 +require_once'connect.php';
 +$name="wang";
 +$sql="DELETE FROM library WHERE name='$name'";
 +if(mysqli_query($con,$sql))
 +{
 +    echo"delete".$name."success!";
 +}
 +
 +
 +select.php
 +<?php
 +require_once'connect.php';
 +$sql="SELECT * FROM library";
 +$temp=mysqli_query($con,$sql);
 +while($row=mysqli_fetch_assoc($temp))
 +{
 +    $data[]=$row;
 +    
 +}
 +foreach($data as $everyData)
 +{
 +    echo $everyData['name'].":".$everyData['price'];
 +    echo "<br>";
 +}
