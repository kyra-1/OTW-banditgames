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
Let's build a powerful find command that targets just those conditions:
   ```bash
  find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null

   ```
   where::   
```find /```: Search the whole filesystem.  
```-type f```: Only look for files (not directories).   
```-size 33c```: File size is exactly 33 bytes.   
```-user bandit7```: File must be owned by bandit7.   
```-group bandit6```: File must be in group bandit6.  
```2>/dev/null"```: Suppresses all the permission denied errors to keep output clean.
   
3. Having identified the odd-one-out file, print out the contents for yourself
   ```bash
   cat [filename]
   ```
4. Voila!, you have the key to next level, Keep hacking, you lil hacker!
