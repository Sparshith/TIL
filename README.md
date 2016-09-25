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
```
 1. Add filename to .gitgnore.
 2. git rm --cached <filename>
 3. Commit and push changes.
 ```
 
