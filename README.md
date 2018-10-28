# wildfly-admin


To prepare an Ubuntu machine:

https://www.howtoforge.com/tutorial/ubuntu-docker/


```
sudo su
sudo apt install docker.io
systemctl start docker
systemctl enable docker
usermod -aG docker ubuntu
```

Commands
```
docker search ubuntu
docker pull ubuntu
docker images
```




*Build the image*
*Either*
Cut'n'Paste
```
FROM jboss/wildfly
RUN /opt/jboss/wildfly/bin/add-user.sh admin Admin#70365 --silent
CMD ["/opt/jboss/wildfly/bin/standalone.sh", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]
```

into Dockerfile

Build with
`docker build -t billys-wildfly .`

*Or*
Build directly with (needs git to be installed)

`docker build github.com/nickdunand/wildfly-admin -t billys-wildfly`

*End Either Or*



*Run Wilddfly*

`docker run -p 8080:8080 -p 9990:9990 -it billys-wildfly`

Set the Security Rules in AWS

https://github.com/nickdunand/wildfly-admin/blob/master/AWSSecurityRules.PNG




To prepare a linux machine:

```
sudo yum update -y
sudo yum install -y docker
sudo service docker start
sudo usermod -a -G docker ec2-user
exit
docker info
```

