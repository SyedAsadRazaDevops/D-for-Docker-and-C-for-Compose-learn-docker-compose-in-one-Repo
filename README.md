# D-for-Docker-and-C-for-Compose-learn-docker-compose-in-one-Repo

![chrome_bXccLt7fbw](https://user-images.githubusercontent.com/71556060/188312771-5a19bb01-6afd-43dd-8e50-f8778b73c5b1.png)

# Docker-Compose: Version ".1"
its limited
- you can define the services directily insted of creating service section
```
mongodb:
        image: mongodb:5.0
    
    mysqldb:
        image: mysql:latest
        
    application:
        image: java_springbot:latest
```
- if you have multiple container on different network so, there is no way to **define on specific location** in YAML file.
- we used **--link** command to connect to each others. `all the conter run on the default "netwok-bridge"`
- there is no ways to **pre ordered sequence** dependentiese for container to run.

# Docker-Compose: Version ".2"
- define the all Services ONE service section.
```
service:
    mongodb:
        image: mongodb:5.0
    
    mysqldb:
        image: mysql:latest
        
    application:
        image: java_springbot:latest
```
- must define the docker-composer verion in the first. 
`version:2`
- it will **Automated create a new default network** and then attached all containers to this network, so you commnicate to each othere by calling services
- container run Sequence role `which container define first will run first and then others as well`.
- also define `depends_on:` to define the sequence and flow of containers. 


# Docker-Compose: Version ".2" [LATEST]
- Define version "3" On the top.
- same service section just like version "2".
- it come with docker `sawarm` feature.





-
