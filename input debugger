<?php
$filename = $file = 'data'.time().'.md';

$data['time'] = date("Y-m-d H:i:s");

// Save headers
$headers = getallheaders();
$data['headers'] = $headers;

// Save POST data
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    $data['POST'] = $_POST;
}

// Save GET data
if (!empty($_GET)) {
    $data['GET'] = $_GET;
}

// Save PUT data
if ($_SERVER['REQUEST_METHOD'] === 'PUT') {
    parse_str(file_get_contents("php://input"), $putData);
    $data['PUT'] = $putData;
}

// Save DELETE data
if ($_SERVER['REQUEST_METHOD'] === 'DELETE') {
    parse_str(file_get_contents("php://input"), $deleteData);
    $data['DELETE'] = $deleteData;
}

$json = json_encode($data);
file_put_contents($filename, $json);

print_r($json);
?>
