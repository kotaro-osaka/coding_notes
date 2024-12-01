**Mark file as executable in path**
(File is run when addressed with `./file_name.py`)
```bash
chmod +x file_name.py
./file_name.py
```
`chmod +x` makes file **executable**

> file must also contain following shebang in first line:
> `#!/usr/bin/env python`
> (replace python with desired interpreter)

---

**Create Virtual Environment (bash)**
create
```bash
$ python -m venv myvenv
```
activate
```bash
$ source myvenv/scripts/activate
```
deactivate
```bash
$ deactivate
```

---

**ROI (return on investment)**
`Time_to_automate < (time_to_perform * amount_of_times_done)`

---

**Reading files**
```python
file = open("file.txt")
file.close()

# or

with open("file.txt") as file:
# ...
```

```python
file.read() # return entire file as String

file.readline() # return line as String
```

absolute/relative path can be used to open file in different directory
___

**Writing Files**
Open file with ==mode==
```python
with open("file.txt", "r") as file: # default read only
with open("file.txt", "w") as file: # write only
with open("file.txt", "a") as file: # append
with open("file.txt", "r+") as file: # read-write
with open("file.txt", "x+") as file: # open for exclusive creation, failing if the file already exists
```

*"w"*: overwrites existing contents

```python
file.write("lorem ipsum")
# when successful, returns value: 30
```

___

**Encoding**
Python distinguishes between binary mode (“b”) and text mode (“t”). By default, files are opened in the text mode, which means you read and write strings from and to the file, which are encoded in a specific encoding.
`f = open('workfile', 'w', encoding="utf-8")`

___

**os module**
`import os`

```python
# remove file
os.remove("file.txt")

# rename file
os.rename("file.txt", "renamed.txt")

# check if file exists (return bool)
os.path.exists("file.txt")
```

More file information
```python
# file size
os.path.getsize("file.txt")

# timestamp
os.path.getmtime("file.txt")

# formated timestamp
import datetime
timestamp = os.path.getmtime("file.txt")
datetime.datetime.fromtimestamp(timestamp)

# absolute path
os.path.abspath("file.txt")
```

Directories
```python
# current working directory
os.getcwd()

# create new directory
os.mkdir("new_dir")

# change cwd
os.chdir("new_dir")

# delete directory
os.rmdir("new_dir")

# list direcotry
os.listdir("new_dir")
```

___

**csv module (comma separated values)**
`import csv`

```python
# read file
csv_f = csv.reader(f)

# close file
csv_f.close()
```

Variables
```python
# unpack values into variables
for row in csv_f:
	name, phone, role = row
	print("Name: {}, Phone: {}, Role: {}".format(name, phone, role))
# can also be addressed by indexes
```

Lists
```python
# write file from lists
data = [[..., ...], [..., ...], [..., ...]]
writer = csv.writer(csv_f)
writer.writerow(data) # writes one row at a time
writer.writerows(data) # writes all rows at once
```

Dictionaries
```python
# read csv to dictionaries
reader = csv.DictReader(csv_f)
for row in reader:
	print(("{} has {} users").format(row["name"], row["users"]))

# write dictionaries to csv
users = [ {...}, {...}, {...}]
keys = ["name", "username", "department"]
with open('csv_f', 'w') as csv_f:
	writer = csv.DictWriter(csv_f, fieldnames=keys)
	writer.writeheader() # names of columns as first line in csv_f
	writer.writerows(users)
```

