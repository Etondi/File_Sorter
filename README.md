# Automatic File Sorter Project

## Table of Contents
1. [Project Overview](#Project-Overview)
2. [Tools](#Tools)
3. [Code](#Code)
4. [Limitations](#Limitations)
5. [References](#References)


## Project Overview
This project involves creating an automatic file sorter using Python. The purpose of the project is to organize files in a specified directory by moving them into folders based on their file types.

## Tools
- Python
- Jupyter Notebook

## Code

```python
# Importing Libraries
import os, shutil

# Define the path where files are located and will be sorted
# Using backslashes due to Windows file path requirements
# Users should update this path to their local directory
path = r"/path/to/your/directory/File Sorter/"

# List all files in the specified directory
file_name = os.listdir(path)
# Print out the list of files for inspection
print("Files in the directory:")
print(os.listdir(path))

# Define folder names for different file types
folder_names = ['jpg files', 'png files', 'pdf files', 'txt files', 'xlsx files']

# Create folders if they don't already exist
for loop in range(0, 5):
    if not os.path.exists(path + folder_names[loop]):
        print(f"Creating folder: {path + folder_names[loop]}")
        os.makedirs(path + folder_names[loop])

# Loop through each file and move it to the corresponding folder based on its extension
for file in file_name:
    if ".jpg" in file and not os.path.exists(path + "jpg files/" + file):
        shutil.move(path + file, path + "jpg files/" + file)
    elif ".png" in file and not os.path.exists(path + "png files/" + file):
        shutil.move(path + file, path + "png files/" + file)
    elif ".pdf" in file and not os.path.exists(path + "pdf files/" + file):
        shutil.move(path + file, path + "pdf files/" + file)
    elif ".txt" in file and not os.path.exists(path + "txt files/" + file):
        shutil.move(path + file, path + "txt files/" + file)
    elif ".xlsx" in file and not os.path.exists(path + "xlsx files/" + file):
        shutil.move(path + file, path + "xlsx files/" + file)
    else:
        print(f"File {file} was not moved. It may already exist in the destination folder or is of an unsupported type.")

print("File sorting complete.")
```
## Limitations
- The script currently only handles five specific file types (jpg, png, pdf, txt, xlsx).
- It doesn't process files that are already in the destination folders or unsupported file types.

## References
- Python Official Documentation: os module
- Python Official Documentation: shutil module
