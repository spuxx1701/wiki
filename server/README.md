# Full server setup guide

## Setup server permissions, connections & security

### Create new (non-root) sudoer

```bash
sudo adduser leo
usermod -aG sudo leo
```

### Create and upload ssh key
On your local machine, create a new ssh key pair.

```bash
ssh-keygen -t rsa
``` 
Choose a name (e.g. the server name) and a passphrase. Then upload the public key to the remote host:

```bash
ssh-copy-id -i ~/.ssh/server_name leo@server_ip_adress
```

Now, add the server to your `~/.ssh/config`:

```bash
Host server_name
    HostName server_ip_adress
    User leo
    IdentityFile ~/.ssh/server_name
```
