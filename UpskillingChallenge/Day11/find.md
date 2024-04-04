## Find Command
- How to search a file based on their size?
```bash
find . -size -50M
```
- How to find only file or directory in a given path?
```bash
find . -name 
```
- How to search a file based on it's name?
```bash
find . -name 
```
- How to ignore upper & lower case in file name while searching?
```bash
find . -iname "Shubbha.txt"
```
- How to search files for a given user only?
```bash
find . -user somnath
```
- How to search a file based on the inode no.?
```bash
find . -inum 9892
```
<!-- - How to search a file based on the no. of links?
```bash

``` -->
- How to search a file based on their permissions?
```bash
find . -perm 777
```
- How to search all the files which start with letter a?
```bash
find . -name "a*"
```
- How to search all the files which are created after last.txt file?
```bash
find ./Learning-Devops -newer shubbha.txt
```
- How to search all the empty files in a given directory?
```bash
find . -empty
```
- How to search all the empty files and delete them?
```bash
find . -empty -exec rm -rf{} \;
```
- How to search all the files whose size are between 1-50 MB
```bash
find . -size +1M -size -50M
```

## Grep
- How can you search for lines containing a specific word in a file using grep?
```bash
find . -size +1M -size -50M
```
What option is used to search recursively in all files in a directory for a specific pattern with grep?
```bash
find . -size +1M -size -50M
```

