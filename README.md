# myphpadmin
PHP/MYSQL
<?php
$connection = mysqli_connect ("localhost", "root", "", "election_database");

if(!$connection){

die("error". mysqli_connect_error());

}

// summed polling unit

echo 'Summed Polling Unit';
$query= "select * from summed_total_of_pu_result";

$stmt =mysqli_query($connection,$query);

while($row= mysqli_fetch_array($stmt, MYSQLI_ASSOC)){

    echo $row ['id'] .  ' ' .$row['party'] . ' ' .$row['pu_result']. '  '  .$row['lga_name']. '  ' .$row['pu_results_id'] .'</br>' ;


}

// polling unit results

echo 'Polling Unit Results:';
$connection = mysqli_connect ("localhost", "root", "", "election_database");

if(!$connection){

die("error". mysqli_connect_error());

}

$query= "select * from pu_results:";

$stmt =mysqli_query($connection,$query);
while($row= mysqli_fetch_array($stmt, MYSQLI_ASSOC)){

    echo $row ['id'] .  ' ' .$row['party'] . ' ' .$row['pu_result']. '  '  .$row['lga_name'] .'</br>' ;


}




?>
