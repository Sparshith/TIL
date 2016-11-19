# Backend

## Python

### Ordered params in requests module for GET calls.
```
	get_params = (('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'))
	r = requests.get(url, params=get_params)
```

## Database
 
### Dropping a user without any errors
```
 GRANT USAGE ON *.* TO 'username'@'localhost';
 DROP USER 'username'@'localhost';
```
### Disabling strict mode on mysql server.
```
SET GLOBAL sql_mode=(SELECT REPLACE(@@sql_mode,'ONLY_FULL_GROUP_BY',''));
```

## PHP 

### Merging two arrays while retaining indexes
```
$a = array(1, 2, 3);
$b = array("a" => 1, "b" => 2, "c" => 3)
$c = $a + $b;
```

$c will now be 
```
array (
  0 => 1,
  1 => 2,
  2 => 3,
  'a' => 1,
  'b' => 2,
  'c' => 3,
);
```

### Finding which php.ini file is being used
Seems like a strange thing to find out, but I recently debugged a problem for quite sometime before realizing that the cli and the webserver were using different php.ini files.
```
php_ini_loaded_file();
```
