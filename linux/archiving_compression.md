# Archiving and Compression

- Archiving: Combines multiple files into one, reducing overhead and making them easier to transmit.
- Compression: - Reduces file size by removing redundant information. When an archive is decompressed and files are extracted, this is called un-archiving.


## Compression
### Lossless
No information is removed. Compressing and then decompressing produces a file identical to the original.
### Lossy
Some information may be removed. The decompressed file is slightly different from the original. Example: two similar shades of green in an image may be treated as the same to reduce size. Often, the difference is imperceptible to the human eye.

### Data Compression Algorithms
- gzip → Lempel-Ziv algorithm
- bzip2 → Burrows-Wheeler algorithm
- xz → Lempel-Ziv-Markov (LZMA) algorithm

| **Command** | **Description** |
| --- | --- |
| `gzip <file>`	| Compressing files. Use Lempel-Ziv data compression algorithm. |
| `gzip -l <file>` | Information about compressed file. |
| `gzip -d <file>`  or `gunzip <file>` | Decompressing files. |
| `bzip2 <file>` | Compressing files. Use Burrows-Wheeler block sorting. |
| `xz <file>` | Compressing files. Use Lempel-Ziv-Markov (LZMA) chain algorithm. |
| `rar a <file1.rar> <file1> <file2> <dir1>` | Compressing file1, file2, and dir1 simultaneously. |
| `rar a <file1.rar> <test_file>` | Create a rar file. |
| `unrar -x <file.rar>`	| Decompressing rar file. |
| `zip <file1.zip> <file1>`	| Create a zip file. |
| `zip -r <file.zip> <dir>`	| Recursion. Compress the directory and its contents. |
| `unzip <file1.zip>`	| Decompressing zip file. |
| `unzip -l <file1.zip>` | List files in .zip archive. |
| `unzip <file.zip> <specificFileToExtract>` | Decompressing zip file. |


## Archiving
TAR = Tape ARchive
The tar command has three useful modes:
- Create: Make a new archive from files.
- Extract: Pull files out of an archive.
- List: Show archive contents without extracting.

### Create mode
| **Command** | **Description** |
| --- | --- |
| `tar -cf <new-archive_tar> <archives>` | Creating an archive with the tar command |
| `tar -czf <new-archive_tar.gz> <archives>` | Creating and compressing an archive with the tar command. The resulting file is compatible with gzip. • **-c** = create a file • **-f**, to specify the name of the .tar file |
| `tar -cjf <new-archive_tbz> <archives>` | Creating and compressing an archive with the tar command. The resulting file is compatible with bzip2. |
| `tar -rvf <udev.tar> </etc/hosts>` | **-r** = To add a file to an existing file |

## List Mode
| **Command** | **Description** |
| --- | --- |
| `tar -tjf <archive_tbz>` | **-t** = list the files in an archive **-f** = operate on the given archive. **-j** = decompress with an bzip2 command. |
| `bunzip2 -c <archive.tbz> \| tar -t` | List the contents of the file |

## Extract Mode
| **Command** | **Description** |
| --- | --- |
| `tar -xjvf <archive_tbz>`	| **-x** = extract files from an archive. **-f** = operate on the given archive. **-j** = decompress with an bzip2 command. **-v** = verbosely list the files processed. |
