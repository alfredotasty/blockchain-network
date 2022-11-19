# blockchain-network
private-blockchin


# How to use 
## create subnetwork
```sh
docker network create --driver bridge testNet

```
## Check ip
```sh     
docker inspect testNet         
```

Change network ip in docker-compose in each node directory to new subnetwork ip by sequently 
```sh
networks:
      testNet:
        ipv4_address: 172.24.0.10
```

And add new subnetwork in docker-compose with new subnetwork ip
```sh
networks:
  testNet:
    ipam:
      config:
        - subnet: 172.24.0.0/16
```
        
## Delete subnet
```sh
docker network prune
```

## Start network
```sh
docker-compose up -d 

```

## Stop network
```sh
docker-compose stop
```
