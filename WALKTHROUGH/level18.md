# 17. `File Difference Detection`

0. Login

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 16 to login.

1. The problem says:

```
There are 2 files in the home directory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new.
```

2. List the files to confirm:

```bash
ls -l
```

You'll see:

```bash
passwords.old  passwords.new
```

3. Use the `diff` command to compare both files:

```bash
diff passwords.old passwords.new
```

This will output the differing line(s). Only one line has changed.

The output will look something like:

```bash
< oldpasswordline
> newpasswordline
```

The line after `>` is the new password.

4. Voila!, you have the key to next level, Keep hacking, you lil hacker!

💡 **Note:**

* If you try logging in to bandit18 and see `Byebye!`, don't worry — it's part of the next level’s challenge!
