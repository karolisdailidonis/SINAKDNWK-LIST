``
ssh-keygen -t ed25519 -C "your_email@example.com"
``

``
cat /home/username/.ssh/.....pub
``

Windows
``
cat C:\Users\USER\.ssh\<key_name>.pub | ssh SSHUSER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
``

```
#Config file

Host bitbucket.org
User git
Port 22
HostName bitbucket.org
IdentityFile ~/.ssh/id_rsa.......
TCPKeepAlive yes
IdentitiesOnly yes
```
