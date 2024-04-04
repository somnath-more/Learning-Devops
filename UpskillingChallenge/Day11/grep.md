## Grep Command
```txt
This is abc file
somnath more is owner of this file
bmw car is my fav
cricker is my passion
```
- How do you search for lines that start with a specific word using grep?
```bash
grep "bmw" abc.txt
```
- What grep option allows you to search for lines that end with a specific word?
```bash
 grep "passion$" abc.txt

```
- Which option in grep enables you to search for lines containing a word while ignoring case distinctions?
```bash
 grep -i "Passion" abc.txt
```
- How can you use grep to search for lines that do not contain a specific word?
```bash
 grep -v "passion" abc.txt
```
- What option is used in grep to interpret the pattern as an extended regular expression?
```bash
 egrep "fav|car" abc.txt
 grep -E "fav|car" abc.txt
```
- How do you count the number of lines containing a specific word in a file using grep?
```bash
 grep -c "fav" abc.txt
```
- Using grep, how can you print lines before and after the matched line?
```bash
 grep -C 1 "fav" abc.txt
```
- Which option in grep allows you to display line numbers along with matched lines?
```bash
 grep -n "fav" abc.txt
```
