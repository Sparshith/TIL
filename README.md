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
Assuming solr is running on 8983,

```
lsof -i :8983
kill -9 PID#

```

## Misc
 
### Removing .php extension from urls using .htaccess
```
RewriteEngine on
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^([^\.]+)$ $1.php [NC,L]
```

