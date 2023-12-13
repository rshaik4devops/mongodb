
# MongoDB

Choose `mongodb` from the list.

## Install MongoDB Manual Steps.

Ref URL: https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-amazon/

1. Setup MongoDB repos.

```
Create a /etc/yum.repos.d/mongodb-org-7.0.repo file so that you can install MongoDB directly using yum
add the below content to the file created above and save the file.
[mongodb-org-7.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2023/mongodb-org/7.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-7.0.asc

```

2. Install Mongo & Start Service.

```
# yum install -y mongodb-org 
# systemctl enable mongod
# systemctl start mongod
```
To interact with mongoshell securely run the below two commands to uninstall mongo non secure shell and install mongo secure shell
# rpm -e --nodeps mongodb-mongosh
# yum install mongodb-mongosh-shared-openssl3.x86_64 -y
```




3. Update Liste IP address from 127.0.0.1 to 0.0.0.0 in config file 

Config file: `/etc/mongod.conf`

then restart the service 

```
# systemctl restart mongod
```

## Every Database needs the schema to be loaded for the application to work.

Download the schema and load it.

```
# curl -s -L -o /tmp/mongodb.zip "https://github.com/rshaik4devops/mongodb/archive/main.zip"

# cd /tmp
# unzip mongodb.zip
# cd mongodb-main
# mongosh < catalogue.js
# mongosh < users.js 

```

 Symbol `<` will take the input from a file and give that input to the command.
