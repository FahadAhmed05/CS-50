# Week (1)

## SSH
### Definition
SSH is also known as Secure Shell.Secure Shell is a network communication protocol that enables two computers to communicate .

## SSH Commands
1. Execute `ssh-keygen`. When prompted to “save the key,” just hit Enter, without typing anything.
2. Execute `cat ~/.ssh/id_rsa.pub`. You’ll then see your “public key,” multiple lines of seemingly random text. Highlight and copy all of those lines, starting with ssh-rsa to the end.
3. Visit (https://github.com/settings/keys), logging in with your GitHub username and password as usual. Don’t use the passphrase you just created, if any. And then create ssh key .
4. Execute `ssh -T git@ssh.github.com -p 443`