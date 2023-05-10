# File handling in python

- We can use the built-in **`open() function`**.

- Pass it a string containing the filename and a second string containing the mode.

- Mode can be **`'r'`** for read mode, **`'w'`** for write mode, **`'a'`** for append mode, and **`'x'`** for explicitly create a new file. If the file already exists, this mode will throw an error.

- We can also specify **`'r+'`** which is reading and writing mode.

- Remember to **always close the file** after you have finished reading it **`to avoid any resource leaks or issues with file locks`**.

---

## Reading a file 📖

- We can **`read a file all at once`** or **`line by line`**.

<br/>

- Be aware of the size of the file you are reading. **If the file is very large**, you might not want to read the entire file into memory at once, as this could use up a lot of memory. Instead, you can **read the file line by line** using a loop.

- When reading files, **`it's important to handle exceptions that can occur`**, such as if the file does not exist or if there are permission issues. You can use try and except blocks to catch and handle these exceptions.

### ~> Reading a file all at once

```python
# Open file for reading
file = open('example.txt', 'r')

# Read the entire contents of the file
file_contents = file.read()

# Close the file
file.close()

# Print the contents of the file
print(file_contents)
```

### ~> Reading a file line by line

```python
# Open file for reading
file = open('example.txt', 'r')

# Read the file line by line
for line in file:
    # Do something with the line
    print(line)

# Close the file
file.close()
```

### ~> Reading a file using try and except

```python

try:
    # Open file for reading
    file = open('example.txt', 'r')

    # Read the entire contents of the file
    file_contents = file.read()

    # Print the contents of the file
    print(file_contents)

except FileNotFoundError:
    print('File does not exist.')

except PermissionError:
    print('You do not have permission to read the file.')

except Exception as e:
    print('Something went wrong while reading the file.')

finally:
    # Close the file
    file.close()
```

---

## Writing to a file ✍️

- Writing to a file in Python is similar to reading a file, but instead of using the 'r' mode, we **`use the 'w' or 'a' mode to write or append to a file, respectively`**.

### ~> Over-Writing to a file

```python
# Open file for writing
file = open('example.txt', 'w')

# Write to the file
file.write('Hello, world!')

# Close the file
file.close()
```

### ~> Appending to a file

```python
# Open file for appending
file = open('example.txt', 'a')

# Append to the file
file.write('\nThis is a new line.')

# Close the file
file.close()
```

<div align="center">
== X ==
</div>