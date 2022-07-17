##  Creating postgresSQL container with db inside, using Docker Compose

- create .env file with this parameters and insert the parameters.

- create docker-compose.yml file and insert the code.

- create .sql file and put it in this structure:

```bash
Project
├── docker-compose.yml (File)
├── docker_postgres_init.sql (File)
```
- run command:
sudo docker-compose up -d

- check to see if container created:
sudo docker ps

- connect to container 
sudo docker exec -it {container_id} bash

- run those those commands
root@b37ca1ca5ef3:/# psql -U postgres

postgres=# SELECT * FROM chinavsindia;

```bash
 Index | China |   India    |    Year    
-------+-------+------------+------------
     1 |  2021 | 1444216102 | 1393409033
     2 |  2020 | 1439323774 | 1380004385
     3 |  2019 | 1433783692 | 1366417756
     4 |  2018 | 1427647789 | 1352642283
     5 |  2017 | 1421021794 | 1338676779
     6 |  2016 | 1414049353 | 1324517250
     7 |  2015 | 1406847868 | 1310152392
     8 |  2010 | 1368810604 | 1234281163
     9 |  2005 | 1330776380 | 1147609924
    10 |  2000 | 1290550767 | 1056575548
    11 |  1995 | 1240920539 |  963922586
    12 |  1990 | 1176883681 |  873277799
    13 |  1985 | 1075589363 |  784360012
    14 |  1980 | 1000089228 |  698952837
    15 |  1975 |  926240889 |  623102900
    16 |  1970 |  827601385 |  555189797
    17 |  1965 |  724218970 |  499123328
    18 |  1960 |  660408054 |  450547675
    19 |  1955 |  612241552 |  409880606
(19 rows)
```

<!-- 
sudo docker exec -it 35e177177321 bash
 -->

 <!-- 
 Good link to create table inside postgres at container creation via .sql file
 https://onexlab-io.medium.com/docker-compose-postgres-initdb-ba0021deef76
  -->

  - For deleting all you can run this commands:

  sudo docker rm -f {dockerID}
  sudo docker rmi $(sudo docker images -aq) --force


  sudo docker ps && sudo docker images