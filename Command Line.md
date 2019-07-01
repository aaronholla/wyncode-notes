# Command Line

> use `.` for everything in commands or everything in current folder.

## Shovel Operator  
- `>>` takes anything before it and shovels it into whats after. Also called redirect operator, takes anything that would have gone to the screen and outputs it to the end of file.
```
echo These are my notes so far >> scratchpad.txt
```

## cat

- will output the contents of the file

## Single Shovel Operator 

- `>` creates new file and then shovels. **WARNING: THIS WILL OVERWRITE ALL CONTENT**

## Move and Copy  
- `mv` and `cp` commands can also move/copy and rename in one command
```
mv test.txt folder/new_name.txt
cp test.txt folder/new_copy.txt
```

- use `-r` flag on commands for recursively editing files (cp, rm, mv folder and anything inside of the folder)

## mkdir
- `-p` flag to input a path to create multiple folders all at once

## ls
- `-R` flag will give all folders and the files inside them
- `-a` flag for hidden files

## find  
- Lets you find files in a directory.
`find .` will give you everything. 

## cd  
- use `cd ~` to go home  
- use `cd -` to go to the previous folder (forward or back just last folder)
- use `cd /` to go to root folder

## wildcard operator
- use `*` as a wildcard 

```
touch monday.txt tuesday.txt happy_days.txt
ls *day*
ls *day.txt
```

## grep
 - lets you search through filenames or outputs
 ``` 
 grep ello /usr/share/dict/words
 ```

## pipe  
 - called a pipeline you can pipe output into next command 
 - use the `|` character to put the output of one command as input into another command  
```
find . | grep needle
history | cut -c 8- | sort | uniq -c | sort -nr | head
```

## curl
 - lets you make web requests will return html document
 ```
curl https://www.w3schools.com/cssref/css_colors.asp > colors.html
 ```

## less  
- get an interactive scrollable and searchable view of files

## tail
 - get last # of lines of a file or input use `-` then number of lines 
 ```
history | tail -50 
 ```

