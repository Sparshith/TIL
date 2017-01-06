# Workspace

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

## Terminal on mac

### Finding instances of a particular term recursively
```
grep -roh <term_to_search> . | wc -w
```

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

### Restarting apache server
```
sudo apachectl restart
```
