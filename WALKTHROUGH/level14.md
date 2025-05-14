# 13. `Private SSH Key Access`

0. Login

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 12 to login.

1. Locate the files in the home directory:

```bash
ls -la
```

You see a file named `sshkey.private`.

2. The problem says:

```
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. You get a private SSH key to log into the next level.
```

Since the file is a private SSH key, we can directly use it to log in to **bandit14**.
First, ensure the key permissions are correct:

```bash
chmod 600 sshkey.private
```

3. Use the private key to SSH into the next level:

```bash
ssh -i sshkey.private bandit14@localhost
```

4. Once logged in as `bandit14`, access the password file:

```bash
cat /etc/bandit_pass/bandit14
```

This will print the password for the next level!

5. Voila!, you have the key to next level, Keep hacking, you lil hacker!
