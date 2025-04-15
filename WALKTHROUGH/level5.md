# 5. FOR loop and File command

0. Login ```ssh bandit4@bandit.labs.overthewire.org -p 2220```
    >Use the password from Level 4 to login.
1. locate the files in the home directory
   ```bash
   ls -la
   ```
   Looks like, theres no file, but a Directory instead
   > Blue coloured items are directory items
2. To inspect the directory, change the current directory
   ```bash
   cd [directory name]
   ```
3. To view the contents of the Directory, including the hidden files, if any,
4. 
    ```bash
   ls -la
   ```
5. looks like, there are a lot of files, and the password could be in any one of the following, manually checking each one would be a tedious task, so lets set up a *FOR* loop in the command line, itself 

   ```bash
   for i in {00..09};do file ./-file$i;done
   ```
   where we used the addressing file location, because of the Dashed filenames
   > "file" command tells us about the type of content stored in the file, we are looking for ASCII text in this level   
   > '$i' is used as a placeholder for the variable value
   
6. Having identified the odd-one-out file, print out the contents for yourself
   ```bash
   cat [filename]
   ```
7. Voila!, you have the key to next level, Keep hacking, you lil hacker!
