# 13. `Hexdump + Multiple Uncompress`

0. Login
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
>Use the password from Level 12 to login.

1. Locate the files in the home directory:
```bash
ls -la
```
You see a file named `data.txt`.

2. The problem says:
```
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.
```

So the file is:
- A **hexdump** of a compressed file
- That file was compressed **multiple times**

We need to reverse the hexdump, and then keep uncompressing the file until we get the password.

---

### Step-by-step:

3. Make a temporary working directory under `/tmp`:
```bash
cd /tmp
mkdir $(mktemp -d)
cd <your_temp_dir>
```

4. Copy the data file into your temp dir:
```bash
cp ~/data.txt .
```

5. Convert the hexdump back to a binary file:
```bash
xxd -r data.txt data.bin
```

6. Now we need to identify the compression type and decompress it accordingly.
Loop through file type detection and decompression:
```bash
file data.bin
```
You might get outputs like:
- gzip compressed data → use `mv` to rename it with `.gz`, then `gunzip`
- bzip2 compressed → rename to `.bz2`, then `bunzip2`
- tar archive → rename to `.tar`, then `tar -xf`

Keep doing:
```bash
mv data.bin data.gz   # or .bz2 or .tar as required
<decompress command>  # gunzip, bunzip2, or tar -xf
file <output file>    # check type again
```
Repeat this process until `file` says it's an ASCII text file.

7. Once you reach the final file, just:
```bash
cat <final file>
```
And you will get the password!

8. Voila!, you have the key to next level, Keep hacking, you lil hacker!

