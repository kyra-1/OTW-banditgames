# 12. `ROT13 Decode`

0. Login
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
>Use the password from Level 11 to login.

1. Locate the files in the home directory
```bash
ls -la
```
You see a file named ```data.txt```.

2. The problem says:
```
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
```

This is a classic **ROT13** cipher (rotate each letter 13 positions forward in the alphabet). To decode it, we can use the `tr` command in Linux.

Here's the command:
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

This command does the following:
- `cat data.txt` : reads the file
- `tr 'A-Za-z' 'N-ZA-Mn-za-m'` : translates each letter 13 positions forward (ROT13)

3. You’ll see the decoded text printed, and within it — the password!

4. Voila!, you have the key to next level, Keep hacking, you lil hacker!

