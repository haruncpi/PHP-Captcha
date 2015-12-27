# PHP-Captcha
This is very simple and lightweight Mathematical Captcha Class. You can easily configure it in your raw php project.

# Documentation
 1. Download the **Mc.class.php** file and add this file in your project.
 2. Implement the class in your project like as example.
 
    [NB:Please don't call Mc::putMcData() before your post request where you check the captcha answer.]
    
    **screenshot:**
    
    ![alt tag](https://raw.githubusercontent.com/haruncpi/php-Captcha/master/screenshot/mc-view.jpg)
    
     **Example Code:**
     
    ```PHP
    <?php 
      require_once 'Mc.class.php';
      if(isset($_POST['submit']) && isset($_POST['answer']))
      {
      	$answer=$_POST['answer'];
      	if($answer==Mc::getMcAnswer())
      	{
      		echo "Correct answer";
      	}
      	else
      	{
      		echo "Incorrect";
      	}
      }
      ?>
      
      <!DOCTYPE html>
      <html lang="en">
      <head>
      	<meta charset="UTF-8">
      	<title>PHP Captcha created by Harun</title>
      </head>
      <body>
      				 <?php Mc::putMcData(); ?>
      	<p>Question: <?=Mc::getMcQuestion();?></p>
      	<form action="" method="POST">
      		<p>Put your answer: <input type="text" name="answer"></p>
      		<input name="submit" type="submit">
      	</form>
      </body>
      </html>
    ```
