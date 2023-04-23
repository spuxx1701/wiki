# Full server setup guide

## Setup server permissions, connections & security

### Create new (non-root) sudoer

```bash
sudo adduser leo
usermod -aG sudo leo
```

### Setup SSH connection

On your local machine, create a new ssh key pair.

```bash
ssh-keygen -t rsa
``` 
Choose a name (e.g. the server name) and a passphrase. Then upload the public key to the remote host:

```bash
ssh-copy-id -i ~/.ssh/server_name leo@server_ip_adress
```

Now, add the SSH private key to your local SSH agent:

```bash
ssh-add ~/.ssh/server_name
```

Finally, add the server to your `~/.ssh/config`:

```bash
Host server_name
    HostName server_ip_adress
    User leo
    IdentityFile ~/.ssh/server_name
```

You can now connect to the remote host via `ssh server_name`.
