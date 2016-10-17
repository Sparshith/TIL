# TIL

## Terminal on mac

###  Extracting .rar files
```
brew install unrar
unrar x <filename>
```

### Resizing images
```
sips -Z 640 <filename>
```
(Z is to maintain aspect ratio)

## Git

### Adding files already getting tracked to gitignore

* If you need it to be removed from the remote repository as well.

 ```
  1. Add filename to .gitgnore.
  2. git rm --cached <filename>
  3. Commit and push changes.
  ```
* If you need to retain in the file from the remote, while ignoring it in the local repo.
 
 ```
 git update-index --assume-unchanged <filename>
 ```
 
## Database
 
### Dropping a user without any errors
 ```
 GRANT USAGE ON *.* TO 'username'@'localhost';
 DROP USER 'username'@'localhost';
 ```

## Installations and setup

### Composer

```
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/
```
And in bash profile (little hacky)
```
vim ~/.bash_profile
alias composer="php /usr/local/bin/composer.phar"
```

### Solr

Use http://mirror.nyi.net/Apache/lucene/solr/ to check for latest versions and download.

```
wget http://mirror.nyi.net/Apache/lucene/solr/6.2.0/solr-6.2.0.tgz
tar xzf solr-6.2.0.tgz
cd solr-6.2.0
```

### Uninstalling Java 1.7 and installing Java 1.8

Got this error while setting up solr on ec2: ``` Exception in thread "main" java.lang.UnsupportedClassVersionError: org/apache/solr/util/SolrCLI : Unsupported major.minor version 52.0 ``` which happens when there is a difference between version of JDK during compile and run time. Solved it by updating to Java 1.8.

```
sudo yum install java-1.8.0
sudo yum remove java-1.7.0-openjdk
```

## Solr

### Starting server
```
bin/solr -e [EXAMPLE]
```

### Stopping server

```
bin/solr stop

```
## Misc
 
### Removing .php extension from urls using .htaccess
```
RewriteEngine on
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^([^\.]+)$ $1.php [NC,L]
```

### Fisher-Yates Shuffle
```
function shuffle(array) {
  var m = array.length, t, i;

  // While there remain elements to shuffle…
  while (m) {

    // Pick a remaining element…
    i = Math.floor(Math.random() * m--);

    // And swap it with the current element.
    t = array[m];
    array[m] = array[i];
    array[i] = t;
  }

  return array;
}
```

### Inbuilt servers (Simpler alternative toinstalling XAMPP/WAMP)
Change directory to your working directory.

Python 2
```
python -m SimpleHTTPServer 80
```
PHP
```
php -S localhost:8000
```


## Frontend
### Specifying font-weights while using google fonts

```
<link rel="stylesheet" type="text/css"
      href="https://fonts.googleapis.com/css?family=PT+Sans:400,500,700">
```

### Downloading with a different filename than what it's original name on the server
```
 <a href="/orginal_name.pdf" download="New name">
```

### Embedding youtube videos
Original link : https://www.youtube.com/watch?v=1ArKekKqg2o
```
  <iframe width="420" height="315" src="https://www.youtube.com/embed/1ArKekKqg2o" frameborder="0" allowfullscreen></iframe>
```

