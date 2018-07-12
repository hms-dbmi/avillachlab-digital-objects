
# NHANES Oracle Database Docker Image: 
## Overview

Database is pre-populated with the CDC NHANES public dataset (41,474 patients with ~1,300 variables)


# Docker Host Hardware Requirements

* Should have minimum 8GB RAM
* 70GB Hard Drive space should be available
* Docker should be installed and running

# How to deploy 


##### Copy below statement and run in terminal window
```java
# docker run --name nhanesdb  -d   -p 1521:1521  dbmi/i2b2transmart-db:oracle.12.2.0.1-ee-i2b2.1.7.09-tm.release-18.1-nhanes 
```

##### Once image is pulled and built, run the below statement to verify database is up and running
```java
# docker logs -f nhanesdb

You should wait to see the message below before proceeding further:

#########################
DATABASE IS READY TO USE!
#########################
```

##### Bash to database (container)
```java
# docker exec -it nhanesdb bash
```
##### Stop database (container)
```java
# docker stop nhanesdb
```
##### Remove database (container)
```java
# docker rm nhanesdb
```
##### Remove image
```java
# docker rmi dbmi/i2b2transmart-db:oracle.12.2.0.1-ee-i2b2.1.7.09-tm.release-18.1-nhanes
```

##### Rebuild image and Container
```java
# docker run --name nhanesdb  -d   -p 1521:1521  dbmi/i2b2transmart-db:oracle.12.2.0.1-ee-i2b2.1.7.09-tm.release-18.1-nhanes
```

##### Next Steps

* Oracle DB is up and running at this point with NHANES dataset. Use Oracle SQLDeveloper or any tools of your choice to connect to the DB. At this point you should reset the password of the database using the ".setPassword.sh" script 

```java
docker exec -it nhanesdb bash
```

and run the .setPassword.sh script in the default directory of nhanesdb docker container.
