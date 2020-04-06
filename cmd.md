### Create text file from querying tables in bulk 
mysqldump -uroot -ppassword -hhostIp -PportNum databaseName tableName --where="startDateTime >='2020-02-28 00:00:00' AND startDateTime<='2020-02-29 23:59:59'" --fields-terminated-by ',' --fields-enclosed-by '"' --fields-escaped-by '\' --lines-terminated-by='\n' --no-create-info --tab /tmp/

### compress data files with extension .txt
tar -zcvf data.tar.gz *.txt

### copy file from server to local machine
scp user@remote.server.ip:/home/user/data.tar.gz /Users/data

### extract data files from compressed file
tar -zxvf data.tar.gz