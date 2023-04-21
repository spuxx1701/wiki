## Copy SSH key to remote machine

```bash
ssh-copy-id -i ~/.ssh/id_rsa.pub YOUR_USER_NAME@IP_ADDRESS_OF_THE_SERVER
``` 

## Setup SSH hosts for quick access
```bash
# ~/.ssh/config
Host myhost
  HostName 123.456.8.9
  User username
  IdentityFile ~/.ssh/id_rsa
```
