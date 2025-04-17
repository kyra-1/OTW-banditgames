# 7. `GREP` Command 

0. Login ```ssh bandit7@bandit.labs.overthewire.org -p 2220```
    >Use the password from Level 7 to login.
    
1. locate the files in the home directory
   ```bash
   ls -la
   ```
  
2. Let's start by exploring the file.
  The problem says:
  >The password for the next level is stored in the file data.txt next to the word millionth   

  Let's use a grep command 
   ```bash
  cat data.txt | grep millionth
   ```
   where::   
```cat data.txt```: Provides data.txt text as input to grep command.  
```grep [word]```: Only look for specific lines containing the word [word].   
   
3. Voila!, you have the key to next level, Keep hacking, you lil hacker!
