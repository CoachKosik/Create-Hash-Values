# Create-Hash-Values

## Objective

In this lab activity, we’ll create hash values for two files and use Linux commands to manually examine the differences.

## Project description

In this scenario, you need to investigate whether two files are identical or different.

Here’s how you'll do this task:
  * First, you’ll display the contents of two files and create hashes for each file.
  * Next, you’ll examine the hashes and compare them.

## Key Features:
  * **Hashing:** The process of generating a unique hash value for a file to verify its integrity.
  * **File Comparison:** Using the cmp command to identify differences between files.
  * **Command-Line Usage:** Demonstrates proficiency in using basic Linux commands for file manipulation and analysis.
  * **Security Analysis:** Applying hashing techniques to detect file modifications and potential security breaches.

## Skills Learned
  * **Hashing Algorithms:** Understanding the concept of hash functions and their use in verifying file integrity.
  * **Command-Line Tools:** Proficiency in using Linux commands like ls, cat, sha256sum, and cmp to manipulate files and compare their contents.
  * **File Integrity Verification:** Ability to identify differences between files by comparing their hash values.
  * **Problem-Solving:** Applying logical reasoning to analyze the results of hash comparisons and draw conclusions about file integrity.
  * **Attention to Detail:** Carefully examining the output of commands and identifying subtle differences in file contents.

## Tools Used
  * **Linux Terminal:** Used for navigating the file system, executing commands, and interacting with the system.
  * **sha256sum:** A cryptographic hash function used to generate a unique hash value for a given file.
  * **cat:** A command-line utility to display the contents of a file.
  * **cmp:** A command-line utility to compare two files byte-by-byte.

## Steps
### Task 1. Generate hashes for files
The lab starts in your home directory, /home/analyst, as the current working directory. This directory contains two files file1.txt and file2.txt, which contain different data.

In this task, you need to display the contents of each of these files. You’ll then generate a hash value for each of these files and send the values to new files, which you’ll use to examine the differences in these values later.

  * Use the ls command to list the contents of the directory.
    * ![hash 1](https://github.com/user-attachments/assets/34f88ad6-c426-4e75-953c-7852db1a258a)
    * Two files, file1.txt and file2.txt, are listed.
  * Use the cat command to display the contents of the 'file1.txt' and 'file2.txt' file:
    * Review the output of the two file contents:
      * ![hash 2](https://github.com/user-attachments/assets/98797afa-3906-49e2-8367-01a753622cad)
  * Do the contents of the two files appear identical when you use the cat command?
    * Yes. The contents of the two files appear identical when you use the cat command to display the file contents.
      * Although the contents of both files appear identical when you use the cat command, you need to generate the hash for each file to determine if the files are actually different.
  * Use the sha256sum command to generate the hash of the 'file1.txt' file and 'file2.txt' file
    * Review the generated hashes of the contents of the two files:
      * ![hash 3](https://github.com/user-attachments/assets/868fc25a-ca49-4ca3-9367-4712b9ef7299)
  * Do both files produce the same generated hash value?
    * No. The generated hash value for file1.txt is different from the generated hash value for file2.txt, which indicates that the file contents are not identical.

### Task 2. Compare hashes
In this task, you’ll write the hashes to two separate files and then compare them to find the difference.
  * Use the sha256sum command to generate the hash of the file1.txt and file2.txt files, and send the output to a new file called file1hash.
  * Now, you should have two hashes written to separate files. The first hash was written to the file1hash file, and the second hash was written to the file2hash file.
  * You can manually display and compare the differences.
  * Use the cat command to display the hash values in the file1hash and file2hash files.
    * Inspect the output and note the difference in the hash values.
      * ![hash 4](https://github.com/user-attachments/assets/c41e5e01-9b6a-47f9-b880-494420108044)
        * *Note: Although the content in file1.txt and file2.txt previously appeared identical, the hashes written to the file1hash and file2hash files are completely different.*
  * Now, you can use the cmp command to compare the two files byte by byte. If a difference is found, the command reports the byte and line number where the first difference is found.
  * Use the cmp command to highlight the differences in the file1hash and file2hash files
    * Review the output, which reports the first difference between the two files:
      * ![hash 5](https://github.com/user-attachments/assets/ac454b8f-b094-4ff4-a5c9-09969f4c1e47)
        * *Note: The output of the cmp command indicates that the hashes differ at the first character in the first line.*
  * Based on the hash values, is file1.txt different from file2.txt?
    * Yes, the contents of the two files are different because the hash values of each file are different.

### Summary
This project demonstrated the use of Linux commands to verify file integrity through hashing. By utilizing sha256sum, cat, and cmp, users can generate unique hash values for files, display their contents, and compare them for discrepancies. This process is essential for ensuring data integrity and detecting potential modifications in sensitive files, making it a valuable tool for security professionals.
