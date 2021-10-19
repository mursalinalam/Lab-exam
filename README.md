# Lab-exam<?php
class db{
  public $con;
   public $error;
public function __construct()
 {
 $dbhost = "localhost";
 $dbuser = "root";
 $dbpass = "";
 $db = "aiub";
 //$tbname="student";
 //$conn = new mysqli($dbhost, $dbuser, $dbpass,$db);

 $this->con = mysqli_connect("localhost", "root", "", "aiub");
           if(!$this->con)
           {
                echo 'Database Connection Error ' . mysqli_connect_error($this->con);
           }

 //return $conn;
 }





public function insert($table_name, $data)
      {
           $string = "INSERT INTO ".$table_name." (";
           $string .= implode(",", array_keys($data)) . ') VALUES (';
           $string .= "'" . implode("','", array_values($data)) . "')";
           if(mysqli_query($this->con, $string))
           {
                return true;
           }
           else
           {
                echo mysqli_error($this->con);
           }
      }




function CloseCon($conn)
 {
 $conn -> close();
 }
}
?>

<!DOCTYPE html>
<html>
<body>
<h1>Please Fill Up The Form </h1>
<form >
	<form>
<table>

<tr>
 <td> <label for="firstname">First name:</label><br></td>
 <td> <input type="text" id="firstname" name="firstname" minlength="5" ></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td><label for="lastname">Last name:</label></td>
 <td><input type="text" id="lastname" name="lastname" minlength="5"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>

<tr>
 <td><label for="email">Email:</label></td>
 <td> <input type="text" id="email" name="email"></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>



  <td>Gender:</td>
  <td><input type="radio" id="gender" name="gender" value="Male">
  <label for="gender">Male</label>
  <input type="radio" id="gender" name="gender" value="Female">
  <label for="gender">Female</label>


</tr>

<tr>
 <td><label for="MobileNumber">Mobile No:</label></td>
 <td> <input type="text" id="MobileNumber" name="MobileNumber"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>

<tr>
  <td>
  <label for="DateofBirth">Date of Birth:</label></td>
  <td>
  <input type="date" id="DateofBirth" name="DateofBirth"></td>

  
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
</tr>

<tr>
 <td><label for="Hsc">HSC Result:</label></td>
 <td> <input type="text" id="Hsc" name="Hsc"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
</tr>

<tr>
 <td><label for="Ssc">SSC Result:</label></td>
 <td> <input type="text" id="Ssc" name="Ssc"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Select a Course You Want To Enroll:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="CSE">CSE</option>
  <option value="EEE">EEE</option>
  <option value="BBA">BBA</option>
  <option value="LAW">LAW</option>
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Chosee a Enrolling Year:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="2021">2021</option>
  <option value="2022">2022</option>
  <option value="2023">2023</option>
  <option value="2024">2024</option>
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Chosee a Enrolling Season:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="Spring">Spring</option>
  <option value="Summer">Summer</option>
  <option value="Fall">Fall</option>
  
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>


  <tr>
   
  <td><button type="button" onclick="alert('Data Successfully Submitted')">Insert Data</button></td>
  </tr>
  </table>
</form>

</body>
</html>
<!DOCTYPE html>
<html>
<body>
<h1>Please Fill Up The Form </h1>
<form >
	<form>
<table>

<tr>
 <td> <label for="firstname">First name:</label><br></td>
 <td> <input type="text" id="firstname" name="firstname" minlength="5" ></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td><label for="lastname">Last name:</label></td>
 <td><input type="text" id="lastname" name="lastname" minlength="5"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>

<tr>
 <td><label for="email">Email:</label></td>
 <td> <input type="text" id="email" name="email"></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>



  <td>Gender:</td>
  <td><input type="radio" id="gender" name="gender" value="Male">
  <label for="gender">Male</label>
  <input type="radio" id="gender" name="gender" value="Female">
  <label for="gender">Female</label>


</tr>

<tr>
 <td><label for="MobileNumber">Mobile No:</label></td>
 <td> <input type="text" id="MobileNumber" name="MobileNumber"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>

<tr>
  <td>
  <label for="DateofBirth">Date of Birth:</label></td>
  <td>
  <input type="date" id="DateofBirth" name="DateofBirth"></td>

  
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
</tr>

<tr>
 <td><label for="Hsc">HSC Result:</label></td>
 <td> <input type="text" id="Hsc" name="Hsc"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
</tr>

<tr>
 <td><label for="Ssc">SSC Result:</label></td>
 <td> <input type="text" id="Ssc" name="Ssc"></td>
</tr>

<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Select a Course You Want To Enroll:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="CSE">CSE</option>
  <option value="EEE">EEE</option>
  <option value="BBA">BBA</option>
  <option value="LAW">LAW</option>
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Chosee a Enrolling Year:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="2021">2021</option>
  <option value="2022">2022</option>
  <option value="2023">2023</option>
  <option value="2024">2024</option>
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>
  
  <tr>
  <td>Chosee a Enrolling Season:</td>
  <td>
  

<select name="course" id="course">
  <option value="SELECT">Select</option>
  <option value="Spring">Spring</option>
  <option value="Summer">Summer</option>
  <option value="Fall">Fall</option>
  
</select>
</td>
</tr>
<tr>
 <td></td>
</tr>
<tr>
 <td></td>
</tr>


  <tr>
   
  <td><button type="button" onclick="alert('Data Successfully Submitted')">Insert Data</button></td>
  </tr>
  </table>
</form>

</body>
</html>
<?php
require('db.php');

$validatefname="";
$validatefname="";
$validatename="";
$validateemail="";
$validatepassword="";
$validatecheckbox="";
$validateradio="";
$validateage="";
$validatefile="";
$L1=$L2=$L3="";

$fname=$lname=$dob=$email=$number=$gender=$hsc=$ssc=$course=$year=$semester="";
if($_SERVER["REQUEST_METHOD"]=="POST")
{
$fname=$_REQUEST["fname"];
$lname=$_REQUEST["lname"];
$email=$_REQUEST["email"];
$dob=$_REQUEST["dob"];
$number=$_REQUEST["number"];
$gender=$_REQUEST["gender"];
$hsc=$_REQUEST["hsc"];
$ssc=$_REQUEST["ssc"];
$course=$_REQUEST["course"];
$year=$_REQUEST["year"];
$semester=$_REQUEST["semester"];


if(empty($_REQUEST["fname"]) || (strlen($_REQUEST["fname"])<5))
{
    $validatefname= "you must First enter name ||";

}
// elseif (!preg_match('/^\w{5,}$/', $fname)) {
//   $validatefname= "you must valid  enter name ||";
// }
else
{
    $fname=$_REQUEST["fname"];
    $validatefname = "your first is ".$fname;
}

if(empty($_REQUEST["number"]) || (strlen($_REQUEST["number"])<11))
{
    $validatefname= "you must phone number ||";

}
// elseif (!preg_match('/^\w{5,}$/', $fname)) {
//   $validatefname= "you must valid  enter name ||";
// }
else
{
    $number=$_REQUEST["number"];
    $validatenumber = "your first is ".$number;
}

if(empty($_REQUEST["dob"]))
{
    $validatename= "you must dob||";

}else {
  echo "";
}
if(empty($_REQUEST["lname"]) || (strlen($_REQUEST["lname"])<5))
{
    $validatename= "you must Last enter name||";

}
else
{
    $name=$_REQUEST["lname"];
    $validatename = " || your last is : ".$lname;
}

if(empty($email) || !preg_match("/^([a-z0-9\+_\-]+)(\.[a-z0-9\+_\-]+)*@([a-z0-9\-]+\.)+[a-z]{2,6}$/ix",$email))
{
    $validateemail="you must enter email ||";
}
else{
    $validateemail= " || your email is\n ".$email;
}


if(isset($_REQUEST["gender"]))
{
    $validateradio= $_REQUEST["gender"];
}
else{
    $validateradio= "please select at least one radio ||";
}


  $data = new db;
   $success_message = '';
$insert_data = array(
         'fname'     =>     mysqli_real_escape_string($data->con, trim($_POST['fname'])),
         'lname'          =>     mysqli_real_escape_string($data->con, $_POST['lname']),
         'email'          =>     mysqli_real_escape_string($data->con, $_POST['email']),
         'dob'          =>     mysqli_real_escape_string($data->con, $_POST['dob']),
         'gender'          =>     mysqli_real_escape_string($data->con, $_POST['gender']),
         'number'          =>     mysqli_real_escape_string($data->con, $_POST['number']),
         'hsc'          =>     mysqli_real_escape_string($data->con, $_POST['hsc']),
         'ssc'          =>     mysqli_real_escape_string($data->con, $_POST['ssc']),
         'course'          =>     mysqli_real_escape_string($data->con, $_POST['course']),
         'year'          =>     mysqli_real_escape_string($data->con, $_POST['year']),
         'semester'          =>     mysqli_real_escape_string($data->con, $_POST['semester'])

    );



    if($data->insert('New_Students', $insert_data))
    {
         echo "data inserted successfully";
    }

}
?>
