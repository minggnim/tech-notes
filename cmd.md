### Create text file from querying tables in bulk 
mysqldump -uroot -ppassword -hhostIp -PportNum databaseName tableName --where="startDateTime >='2020-02-28 00:00:00' AND startDateTime<='2020-02-29 23:59:59'" --fields-terminated-by ',' --fields-enclosed-by '"' --fields-escaped-by '\' --lines-terminated-by='\n' --no-create-info --tab /tmp/

### compress data files with extension .txt
tar -zcvf data.tar.gz *.txt

### copy file from server to local machine
scp user@remote.server.ip:/home/user/data.tar.gz /Users/data

### extract data files from compressed file
tar -zxvf data.tar.gz

## SSH Tunneling 
```
ssh -L 8000:localhost:8888 user@remote-server
```

## Adding SSH key to ssh-agent and enable agentforward 

### To verify that ssh-agent is running on your computer,
```
$ echo "$SSH_AUTH_SOCK"
```

### Edit .ssh/config file and add the following

```
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
  
  ForwardAgent yes
```

### Add to Mac keychain, as in OSX ssh-agent will "forget" this key, once it gets restarted during reboots.
```
$ ssh-add -K ~/.ssh/id_rsa
```

### Reference https://developer.github.com/v3/guides/using-ssh-agent-forwarding/