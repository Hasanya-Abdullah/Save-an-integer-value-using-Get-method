# Save-an-integer-value-using-Get-method with php
The steps might be a bit long, but they are very easy:
# Part I: Local server setup
1- Open your browser and type "XAMPP download" then download the suitable version for your pc.
2- Save the XAMPP file on your C: or D: file (Preferably on D: because it will take some space).
3- Go to the search icon on your pc and find "Xampp control pannel" then open it.
4- Click on the start buttons of Apache and MySQL.
5- Go to your 

# Part II: Data Base setup
1- Go to your browser and paste the following link "http://localhost/phpmyadmin".
2- Click "New" and write a name for your DB (My DB name is integers) then click on "create" to make a new database.
3- Write the table name (my table name is numbers) then select the columns number (my table has 2 columns) and click "Go".
4- Write the two columns' names and choose their suitable datatype (My two colums names are id and num they both have the datatype INT, and for id, I checked the AI section for auto increment) then click "save".

# Part III: Coding ( you can find the code in the getINT.php file)
1- The database connection:

define('DB_SERVER', 'localhost');
define('DB_USERNAME', 'root');
define('DB_PASSWORD', '');
define('DB_NAME', 'integers');

try{
    $pdo = new PDO("mysql:host=" . DB_SERVER . ";dbname=" . DB_NAME, DB_USERNAME, DB_PASSWORD);
    $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch(PDOException $e){
    die("ERROR: Could not connect. " . $e->getMessage());
}

2- Define a variable for the data:

$data= $_GET['data'];

3- Insert the record in the DB:

$sql = "INSERT INTO numbers (num) values ('$data')";    
if($pdo->exec($sql)===TRUE);
  echo "The record $data has been saved successfully";




