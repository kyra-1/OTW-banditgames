# 11. `Base64 Decode`

0. Login
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
>Use the password from Level 10 to login.

1. Locate the files in the home directory
```bash
ls -la
```
You see a file named ```data.txt```.

2. The problem says:
```
The password for the next level is stored in the file data.txt, which contains base64 encoded data.
```

So, base64 is an encoding format. If we decode it, we’ll get back the original content, which includes our password.

To decode it, simply run:
```bash
base64 -d data.txt
```
Or alternatively:
```bash
cat data.txt | base64 -d
```

This will decode the base64 string and reveal the password.

3. Voila!, you have the key to next level, Keep hacking, you lil hacker!

