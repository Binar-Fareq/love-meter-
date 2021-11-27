# love-meter-
create love meter with php and save file in text document
source code
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>love meter</title>
</head>
<body>
      <style type="text/css">
        body{
          background-image:url('img/love2.jpg') ;
          background-repeat: no-repeat;
          background-size: cover;
        }
        form{
          font-family: "Forte";
          font-size: 35px;
          text-align: center;
          margin: 20px;	
        }
        .ipt{
          font-family: "Budmo Jiggler";
          padding: 10px;
          margin: 0;
          font-size: 25px;
          border: 1px solid white;
          background-image: linear-gradient(90deg,white,red);
          border-radius: 15px;
          width: 200px;
          height: 30px;
          outline: none;
          box-shadow: 2px 4px 5px black;
          text-align: center;
          color: white;
        }

        .sub{
          font-family: "Forte";
          padding: 10px;
          margin: 0;
          font-size: 25px;
          border: 1px solid white;
          background-color: red;
          border-radius: 15px;
          width: 200px;
          height: 50px;
          outline: none;
          box-shadow: 2px 4px 5px black;
          text-align: center;
          color: white;
        }
        .rslt{
          font-size: 28px ;
          color: red;
          font-family:"Kristen ITC" ;
          text-align: center;
        }
	</style>
	<form action="" method="get">
        <h1 style="color: red;">LOVE METER</h1>
        <img src="./img/man.png" width="50" height="50" />&nbsp;<input class="ipt" type="text" name="boyname" placeholder = "Boy Name" required >
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        <img src="./img/woman.png" width="50" height="50" />&nbsp;<input class="ipt" type="text" name="girlname" placeholder = "Girl Name"required><br><br>
        <input class="sub" type="submit" name="sub" value="start"><br>
        <p class="rslt"></p>

      </form>
      <?php
      if (isset($_GET['sub'])) {
        $boy= $_GET['boyname'];
        $girl= $_GET['girlname'];
        $rand= rand(30,100);

        $filename="LoveData.txt";

        //red from file

        $old_data=file_get_contents($filename);
        $content =$_GET['boyname']." , ".$_GET['girlname']."\n";
        $new_data=$old_data.$content;

        //write to file

        file_put_contents($filename, $new_data);
        
        echo "<p class='rslt'>".$boy ."  &  ".$girl."  =   %".$rand."</p>";
      }
      ?>
</body>
</html>
