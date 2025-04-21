# 9. `SORT and UNIQ` Command 

0. Login ```ssh bandit8@bandit.labs.overthewire.org -p 2220```
    >Use the password from Level 8 to login.
    
1. locate the files in the home directory
   ```bash
   ls -la
   ```
   you see a file named ```data.txt```
  
2. The problem says:
  ```The password for the next level is stored in the file data.txt and is the only line of text that occurs only once```
So, if we sort the file, all the same lines will occur together, therefore: ```sort data.txt```
and instead of saving it in another file, we will provide this sorted file contents to ```uniq``` command as input, with a lot of options available, you can check them out with ```uniq --help``` command.   
To only output the unique text line, we will use the ```-u``` option,
  so the final command becomes:
    ```bash
    sort data.txt | uniq -u
    ```
   This will output the unique line, thus the password!
   
3. Voila!, you have the key to next level, Keep hacking, you lil hacker!
