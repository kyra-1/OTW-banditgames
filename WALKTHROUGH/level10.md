# 10. `Strings and Grep`

0. Login
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
>Use the password from Level 9 to login.

1. Locate the files in the home directory
```bash
ls -la
```
You see a file named ```data.txt```.

2. The problem says:
```
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several '=' characters.
```

So, if we use `strings` command, it will extract human-readable text from a binary or weird file.
Thus:
```bash
strings data.txt
```
This will show only printable readable strings from the file.

Since the password line is specifically mentioned to be preceded by several '=' characters, we can use `grep` to filter such lines:
```bash
strings data.txt | grep '='
```

This command will:
- `strings data.txt` : extract readable strings
- `| grep '='` : select only the ones having '=' (multiple '=')

3. Observing the output:
We get output like:
```
,k=?
@k*=
========== the
#e=in
g+=ypF
ea=+
K>=*<
========== password{k
=========== is
1R=j/
e=<2g%
+G/YD=
=wDk
=3?lOt
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
=D!f
H =sS,,
```
Looking closely, after a lot of equal signs (`=`), we find:
```
========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
Thus, **FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey** is the password.

4. Voila!, you have the key to next level, Keep hacking, you lil hacker!

