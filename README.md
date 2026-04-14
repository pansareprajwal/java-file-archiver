# Secure File Packer & Unpacker

## 📌 Overview
The **Secure File Packer & Unpacker** is a Java-based utility designed to consolidate multiple text files from a specific directory into a single, encrypted archive file. It provides a custom archiving solution that not only merges data for easier storage and transfer but also secures it using bitwise encryption techniques.

## 🚀 Core Features & Concepts Used
* **Custom File Archiving:** Merges multiple `.txt` files into a single packed file format without using external compression libraries.
* **XOR Bitwise Encryption:** Secures the internal data of the packed files using an XOR operation (Key: `0x11`), preventing unauthorized plain-text viewing.
* **Custom Header Architecture:** Implements a dynamic 100-byte header for each file packed inside the archive. This header securely stores the original filename, file size, and dynamic padding.
* **Java Core I/O:** Extensive use of Java's core byte-oriented streams (`FileInputStream`, `FileOutputStream`) for fast and memory-efficient data processing.
* **Directory Traversal:** Automatically scans user-defined directories to fetch, process, and pack all relevant text files in one execution.

## 🧠 System Architecture (How it Works)
### The Packing Process:
1. **Directory Scanning:** The program accepts a directory path and scans for all `.txt` files.
2. **Header Generation:** For every file found, the program generates a structured **100-byte header** containing:
   `[Original File Name] + [Space] + [Original File Size] + [Padding Spaces to reach 100 bytes]`
3. **Encryption & Writing:** The 100-byte header is written to the new archive file, followed by the original file's contents, which are encrypted byte-by-byte using an XOR operation before being appended.

## 💻 How to Compile and Run

### Prerequisites
* Java Development Kit (JDK) installed on your system.

### Steps to Execute the Packer
1. Clone the repository to your local machine.
2. Open your terminal or command prompt in the project directory.
3. Compile the Java file:
   ```bash
   javac SecureFilePacker.java
java SecureFilePacker

👨‍💻 Author
Prajwal Sanjay Pansare

GitHub: @pansareprajwal

LinkedIn: Prajwal Pansare
