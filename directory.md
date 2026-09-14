# Directory Reference

A clean, structured reference of common directory and file-management commands across Python, Windows CMD, and Ubuntu/Linux.

## Show current directory

### Python
`os.getcwd()`

### Windows CMD
`cd`

### Ubuntu/Linux
`pwd`


## Change directory

### Python
`os.chdir("")`

### Windows CMD
`cd ""`

### Ubuntu/Linux
`cd ""`


## Create directory

### Python
`os.mkdir("")`

### Windows CMD
`mkdir`

### Ubuntu/Linux
`mkdir`


## List contents

### Python
`os.listdir()`

### Windows CMD
`dir`

### Ubuntu/Linux
`ls`


## Create file

### Python
`open("file.txt", "w")`

### Windows CMD
`type nul > file.txt`

### Ubuntu/Linux
`touch file.txt`


## Display file

### Python
`os.system("type file.txt")`

### Windows CMD
`type file.txt`

### Ubuntu/Linux
`cat file.txt`


## Delete/remove file

### Python
`os.remove("file.txt")`

### Windows CMD
`del file.txt`

### Ubuntu/Linux
`rm file.txt`


## Delete/remove empty directory

### Python
`os.rmdir("")`

### Windows CMD
`rmdir` / `rd`

### Ubuntu/Linux
`rmdir`


## Delete directory + contents

### Python
`shutil.rmtree("")`

### Windows CMD
`rmdir /s`

### Ubuntu/Linux
`rm -r`
