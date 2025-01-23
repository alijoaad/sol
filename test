<?php
require_once('../control/lock.php');
$dept = $_SESSION['SDpt'];
$user = $_SESSION['user_id'];
$type = $_POST['type'];

$IMG = isset($_FILES["filesToUpload"]["name"]) ? $_FILES["filesToUpload"]["name"] : array();
$img_count = count($IMG);

if (empty($_POST['op']))
  $op = "''";
else
  $op = "'" . $_POST['op'] . "'";

  if (empty($_POST['no_depend']))
  $no_depend = "''";
else
  $no_depend = "'" . $_POST['no_depend'] . "'";

if (empty($_POST['d_depend']))
  $d_depend = "'0000-00-00'";
else
  $d_depend = "'" . $_POST['d_depend'] . "'";

  if (empty($_POST['no_order']))
  $no_order = "''";
else
  $no_order = "'" . $_POST['no_order'] . "'";

  if (empty($_POST['cost_dept']))
  $cost_dept = "''";
else
  $cost_dept = "'" . $_POST['cost_dept'] . "'";

  if (empty($_POST['order_infor']))
  $order_infor = "''";
else
  $order_infor = "'" . $_POST['order_infor'] . "'";

if (empty($_POST['name_dep']))
  $name_dep = "''";
else
  $name_dep = "'" . $_POST['name_dep'] . "'";


  if (empty($_POST['mo_order']))
  $mo_order = "''";
else
  $mo_order = "'" . $_POST['mo_order'] . "'";

$uniqeId = $dept . date("YmdHis");

 $ins = "INSERT into  idc_cost.cost_data
        (op,no_depend,d_depend,no_order,order_infor,name_dep,mo_order,cost_dept)
      values
        ($op,$no_depend,$d_depend,$no_order,$order_infor,$name_dep,$mo_order,$cost_dept)";
$ex = mysqli_query($drillingConn, $ins) or die('error-70');

foreach (array_combine($_POST['nam'], $_POST['val'] )as $nam => $val)
  $inss[]='("'.$_POST['op'].'","'.$nam.'","'.$val.'")';
//var_dump($inss);
$fins=implode(',',$inss);
 $inss="INSERT into idc_cost.tm (op, no_tbw, cost_tbw) values $fins";
$ex=mysqli_query($drillingConn,$inss) or die ("false insert");


// $last_ins = mysqli_insert_id($drillingConn);

header("refresh:0.0; url=index.php?status=done");
