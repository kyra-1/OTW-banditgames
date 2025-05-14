# 14. `Port Communication`

0. Login

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 13 to login.

1. The problem says:

```
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.
```

2. To communicate with the port, we can use the **netcat (nc)** command.
   Netcat is used to connect to network sockets.

3. Execute the command:

```bash
echo "<current_password>" | nc localhost 30000
```

Replace `<current_password>` with the password from the previous level.

Explanation:

* `echo` sends the password as input
* `| nc localhost 30000` sends it to port 30000 on localhost

4. You will receive the password for the next level as a response.

5. Voila!, you have the key to next level, Keep hacking, you lil hacker!
