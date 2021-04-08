
# MongoDB

Choose `mongodb` from the list.

## Install MongoDB Manual Steps.

Ref URL: https://docs.mongodb.com/manual/tutorial/install-mongodb-on-red-hat/

1. Setup MongoDB repos.

```
echo '[mongodb-org-4.2]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.2/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.2.asc' >/etc/yum.repos.d/mongodb.repo
```

2. Install Mongo & Start Service.

```
# yum install -y mongodb-org 
# systemctl enable mongod
# systemctl start mongod
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
# curl -s -L -o /tmp/mongodb.zip "https://github.com/roboshop-devops-project/mongodb/archive/main.zip"

# cd /tmp
# unzip mongodb.zip
# cd mongodb-main
# mongo < catalogue.js
# mongo < users.js 

```

 Symbol `<` will take the input from a file and give that input to the command.
