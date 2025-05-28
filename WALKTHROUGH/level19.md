# 19. `Bypass .bashrc Auto-Logout`

0. Login

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 18 to login.

1. The problem says:

```
The password for the next level is stored in a file readme in the home directory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.
```

2. To bypass the `.bashrc` execution, we can avoid starting an interactive shell. Use the `cat` command directly from SSH:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

> Enter the Level 17 password when prompted.

This directly executes the command without invoking an interactive shell, hence `.bashrc` won't run, and you won’t get logged out.

3. You’ll see the password for the next level printed to your terminal.

4. Voila!, you have the key to next level, Keep hacking, you lil hacker!
