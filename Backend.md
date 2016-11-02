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
