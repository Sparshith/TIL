
## Installations and setup

### ZSH on Ubuntu
```
apt-get install zsh
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
sudo vim /etc/pam.d/chsh => comment auth required pam_shells.so
sudo chsh $USER -s $(which zsh)
=> Logout/Login
```



### Redis
* Download source code
 ```
 wget http://download.redis.io/redis-stable.tar.gz
 tar xvzf redis-stable.tar.gz
 cd redis-stable
 ```

* Install dependencies
 ```
 yum groupinstall 'Development Tools'
 cd deps
 make hiredis lua jemalloc linenoise geohash-int
 ```

* Install from source code
 ```
 make
 ```

* Run server
 ```
 redis-server
 ```

* To keep it running as a daemon
 ```
 redis-server --daemonize yes
 ```

* Ping to test
 ```
 redis-cli ping
 ```

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

### Babel
```
sudo npm install -g babel-cli
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
## Babel 
```
babel --presets es2016,react  <directory with jsx> --out-dir <directory to save js files>
```

## htaccess
 
### Removing .php extension from urls 
  ```
  RewriteEngine on
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteRule ^([^\.]+)$ $1.php [NC,L]
```

### Enabling gzip
```
  AddOutputFilterByType DEFLATE text/plain
  AddOutputFilterByType DEFLATE text/html
  AddOutputFilterByType DEFLATE text/xml
  AddOutputFilterByType DEFLATE text/css
  AddOutputFilterByType DEFLATE application/xml
  AddOutputFilterByType DEFLATE application/xhtml+xml
  AddOutputFilterByType DEFLATE application/rss+xml
  AddOutputFilterByType DEFLATE application/javascript
  AddOutputFilterByType DEFLATE application/x-javascript
```
