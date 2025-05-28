# 17. `Port Scan & SSL Identification`

0. Login

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

> Use the password from Level 16 to login.

1. The problem says:

```
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. Only one will give the next credentials.
```

2. Create a temporary working directory (optional but clean):

```bash
mkdir /tmp/bandit16_tmp && cd /tmp/bandit16_tmp
```

3. Scan for open ports in the range 31000–32000:

```bash
for p in {31000..32000}; do
  timeout 1 bash -c "</dev/tcp/localhost/$p" 2>/dev/null && echo "Port $p is open"
done
```

Note the ports that respond.

4. Test each open port to identify SSL/TLS support:

```bash
openssl s_client -connect localhost:<port>
```

If the SSL/TLS handshake succeeds (no error or garbage), it's an SSL/TLS-enabled port.

5. For non-SSL ports, test using `nc`:

```bash
echo "<current_password>" | nc localhost <port>
```

6. For SSL-enabled port, use:

```bash
echo "<current_password>" | openssl s_client -connect localhost:<ssl_port>
```

One of the ports will return the **username and password for the next level**.

💡 **Note:**

* You may get back what you sent on most ports. The correct server will send back something that looks like actual credentials (e.g., `bandit17:password`).
* If you encounter **RENEGOTIATING** or **DONE**, refer to `man openssl` under **CONNECTED COMMANDS**.

7. Voila!, you have the key to next level, Keep hacking, you lil hacker!
