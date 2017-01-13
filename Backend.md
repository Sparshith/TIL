# Backend

## Python

### Ordered params in requests module for GET calls.
```
	get_params = (('key1', 'value1'), ('key2', 'value2'), ('key3', 'value3'))
	r = requests.get(url, params=get_params)
```
### Pretty print JSON.
```
your_json = '["foo", {"bar":["baz", null, 1.0, 2]}]'
parsed = json.loads(your_json)
allMatchesJson = json.dumps(parsed, indent=4, sort_keys=True)
```

### Excecuting files in Python3.
execfile() is not supported in python3. :( This has to be used instead.
```
exec(open("filename.py").read())
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

### Finding the difference between two dates in months
$d1 and $d2 are DateTime Objects.
```
$d1->diff($d2)->m + ($d1->diff($d2)->y*12)
```


### References
```
http://stackoverflow.com/questions/12943819/how-to-python-prettyprint-a-json-file
http://stackoverflow.com/questions/436198/what-is-an-alternative-to-execfile-in-python-3-0
http://stackoverflow.com/questions/4233605/elegant-way-to-get-the-count-of-months-between-two-dates
```
