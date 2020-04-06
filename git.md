## Adding SSH key to ssh-agent
## and enable agentforward 

Edit .ssh/config file and add the following

```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
  
  ForwardAgent yes
```
  
  
## Tunneling 
```
ssh -L 8000:localhost:8888 user@remote-server
```
