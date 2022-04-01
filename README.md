# docker-sftp-nifi

Using MacBook Pro and installed Docker desktop version

Launch SFTP Docker container
Ref: https://hub.docker.com/r/atmoz/sftp

```
# Docker Pull Command
docker pull atmoz/sftp

# Let's mount a directory and set UID:
docker run \
    -v <host-dir>/upload:/home/foo/upload \
    -p 2222:22 -d atmoz/sftp \
    foo:pass:1001
    
docker run \
    -v /Users/pavanchalla/Documents/work/selflearning/mysftpdir/upload:/home/foo/upload \
    -p 2222:22 -d atmoz/sftp \
    foo:pass:1001
```

Check if SFTP is accessible by using below command on Macbook terminal

```
 $ sftp -P 2222 foo@localhost
foo@localhost's password:
Connected to localhost.
sftp>
```
Launch NiFi Docker container
ref: https://hub.docker.com/r/apache/nifi/

```
# Docker Pull Command
docker pull apache/nifi

#Running a container
# Standalone Instance secured with HTTPS and Single User Authentication
# The minimum to run a NiFi instance is as follows:

docker run --name nifi \
  -p 8443:8443 \
  -d \
  -e SINGLE_USER_CREDENTIALS_USERNAME=admin \
  -e SINGLE_USER_CREDENTIALS_PASSWORD=ctsBtRBKHRAx69EqUghvvgEvjnaLjFEB \
  apache/nifi:latest
```

This will provide a running instance, exposing the instance UI to the host system on at port 8443, viewable at https://localhost:8443/nifi