# 7. `FIND` Command with User, Group & File Size

0. Login ```ssh bandit6@bandit.labs.overthewire.org -p 2220```
    >Use the password from Level 6 to login.
1. locate the files in the home directory
   ```bash
   ls -la
   ```
   Looks like, theres no file/Directory
  
2. Let's start by exploring the file system. But since the password isn't in your home directory, and the question says "somewhere on the server", we'll need to search everywhere.
  The problem says:
  >The password for the next level is stored somewhere on the server and has all of the following properties:
  >  owned by user bandit7
  >  owned by group bandit6
  >  33 bytes in size  
3. To view the contents of the Directory, including the hidden files, if any,
5. 
    ```bash
   ls -la
   ```
6. looks like, there are a lot of files, and the password could be in any one of the following, manually checking each one would be a tedious task, so lets set up a *find* command for the specific kind of file we need, i.e.,
   
   >The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:   
   >1. human-readable   
   >2. 1033 bytes in size   
   >3. not executable

   ```bash
   find inhere -type f -size 1033c ! -executable -exec file {} \; | grep "ASCII text"
   ```
   where::   
```find inhere```: Start looking inside the inhere directory.   
```-type f```: Only look for files (not directories).   
```-size 1033c```: File size is exactly 1033 bytes.   
```! -executable```: File is not executable.   
```-exec file {} \;```: For each file, show its type.   
```grep "ASCII text"```: Only keep files that are human-readable.
   
7. Having identified the odd-one-out file, print out the contents for yourself
   ```bash
   cat [filename]
   ```
8. Voila!, you have the key to next level, Keep hacking, you lil hacker!
