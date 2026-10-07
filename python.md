# Python 

Quick reference for installing Python, managing virtual environments and packages, and running basic Python commands.

## Install Python

### Windows

```powershell
winget install Python.Python.3
```

### Linux

```bash
sudo apt install python3
sudo apt install python3-pip
```

## Check Versions

```bash
python --version
python3 --version

python -m pip --version
python3 -m pip --version
```

## Virtual Environment

### Create

```bash
python3 -m venv venv1
```

### Activate

Windows:

```cmd
venv1\Scripts\activate
```

Linux:

```bash
source venv1/bin/activate
```

### Deactivate

```bash
deactivate
```

## pip

### Install Package

```bash
python3 -m pip install <package>
```

### Show Package Version

```bash
python3 -m pip show <package>
```

### Uninstall Package

```bash
python3 -m pip uninstall <package>
```

### Upgrade Package

```bash
python3 -m pip install --upgrade <package>
```

### List Packages

```bash
python3 -m pip list
```

### Freeze Packages

```bash
python3 -m pip freeze
```

### Save Packages

```bash
python3 -m pip freeze > requirements.txt
```

### Install from Requirements

```bash
python3 -m pip install -r requirements.txt
```

## Python

### Run a Script

```bash
python3 script.py
```

### Start Python

```bash
python3
```

### Import a Module

```python
import os
```

```python
import json
```

```python
import requests
```

## `os`

### Run System Command

Windows:

```python
os.system("ipconfig")
```

Linux:

```python
os.system("ls")
```

### Current Directory

```python
os.getcwd()
```

### Change Directory

```python
os.chdir("C:\\Users\\Neo\\Documents")
```

### List Directory

```python
os.listdir()
```

### Create Directory

```python
os.mkdir("folder")
```

### Remove File

```python
os.remove("file.txt")
```

## Basic Functions

```python
print()
type()
len()
```

### Examples

```python
print("Hello")
type(variable)
len(variable)
```

## Common String Methods

```python
.startswith("")
.lower()
.upper()
.replace("", "", 1)
.split("")
.splitlines()
.format()
```

## Common List Methods

```python
.append()
.insert()
.pop()
.extend()
.count()
.sort()
```

## Common Dictionary Methods

```python
.keys()
.values()
.get()
.update()
```

## Useful Formatting

### f-string

```python
f"My name is {name} and my age is {age}"
```

### String Concatenation

```python
"My name is " + name + " and my age is " + str(age)
```

### New Line

```python
"\n"
```
