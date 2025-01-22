*Company*: CODETECH IT SOLUTIONS  

*Name*  : KHUSHBOO KUMARI

*Id*: CT08HQE

*Domain*: CYBER SECURITY AND ETHICAL HACKING  

*Batch Duration*: Dec 30th 2024 to Jan 30th, 2025 

*Mentor Name*: NEELA SANTHOSH
---

# File Hash Comparison Tool

This script scans a specified directory, computes the MD5 hash of each file, and compares it against a set of known hashes loaded from a specified hash file. It's designed to help identify files that may match known malicious or suspicious files, often used in cybersecurity tasks.

## Features

- **Directory Traversal**: Recursively walks through all files in the given directory and its subdirectories.
- **MD5 Hashing**: Calculates the MD5 hash for each file encountered.
- **Hash Comparison**: Compares each file’s hash against a list of known hashes stored in a file.
- **Memory Usage Monitoring**: Tracks memory usage during execution and raises warnings if memory consumption exceeds a threshold.
- **Error Handling**: Includes handling for file-related errors such as permission issues, file not found, and general I/O problems.
- **Progress Updates**: Displays real-time progress updates after processing every 10 files.

## Installation

Ensure you have Python 3.x installed along with the necessary libraries. You can install the required dependencies using the following commands:

```bash
pip install psutil
```

## Usage

To run the script, use the following command:

```bash
python file_hash_checker.py <directory_to_scan> <hash_file_path>
```

- `<directory_to_scan>`: Path to the directory containing the files to scan.
- `<hash_file_path>`: Path to the file containing the list of known hashes (one hash per line).

Example:

```bash
python file_hash_checker.py "/path/to/directory" "/path/to/hashes.txt"
```

## Script Details

- **MD5 Hashing**: The script computes the MD5 hash of each file to compare against the known hashes. This is a basic, but fast, method for identifying files that match known malicious hashes.
- **Memory Usage**: The script keeps track of memory usage using the `psutil` library. It will print a warning if memory consumption exceeds a predefined threshold (default is 300 MB).
- **File Processing**: The script processes files in chunks (4096 bytes at a time) for efficient handling of large files. 
- **Progress Feedback**: After every 10 files, the script prints a status update indicating how many files have been processed so far.

## Example Output

```bash
Initial memory usage: 45.00 MB
Total files to be scanned: 2000
Processed 10 files...
Processed 20 files...
Processed 30 files...
...
Finished processing. Total files processed: 2000
Number of hashes used for comparison: 150
Time taken: 12.34 seconds
No matching hashes found.
```

## Error Handling

The script is designed to handle common file errors gracefully:
- **PermissionError**: If the script does not have permission to access a file, it will print a message and continue.
- **FileNotFoundError**: If the file doesn't exist, it will print a message and continue.
- **IOError**: For general I/O errors, the script prints the error details.
- **Generic Exception**: Any other exceptions are captured and printed.

## Memory Usage Threshold

You can adjust the memory usage threshold by modifying the `MEMORY_THRESHOLD_MB` variable in the script. The default threshold is set to 300 MB.

## Contributing

Feel free to fork this repository, open issues, and submit pull requests. Contributions to improve performance, add features, or fix bugs are always welcome!

---

This `README.md` file provides a high-level overview of the script, including how to install, use, and modify it. It highlights key functionalities like memory monitoring, hash comparison, and error handling.
