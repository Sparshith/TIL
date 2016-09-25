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

 
