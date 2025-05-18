# 16. `SSL/TLS Communication`

0. Login

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 15 to login.

1. The problem says:

```
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
```

2. To communicate securely over SSL/TLS, we use the **openssl s\_client** command:

Execute the command:

```bash
openssl s_client -connect localhost:30001
```

3. Once connected, it will show some SSL/TLS handshake information.
   Now, manually enter the current password:

```
<type the current password>
```

4. You will receive the password for the next level as a response!

💡 **Troubleshooting Tips:**

* If you encounter messages like **DONE**, **RENEGOTIATING**, or **KEYUPDATE**, refer to the **CONNECTED COMMANDS** section of the `openssl` manpage.
* Make sure to enter the password after the connection is established.

5. Voila!, you have the key to next level, Keep hacking, you lil hacker!
