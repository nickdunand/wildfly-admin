# wildfly-admin

Build with

`docker build github.com/nickdunand/wildfly-admin`

run with

`docker run -p 8080:8080 -p 9990:9990 -it jboss/wildfly-admin`


To prepare a linux machine:

```
sudo yum update -y
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker ec2-user
exit
docker info
```
