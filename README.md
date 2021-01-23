# Purencool DB 


Purencool DB is an Application that runs in your browser locally.


## Getting Started

These instructions will cover usage information and for the docker container 

### Prerequisites

In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Usage

#### Container Parameters

Start service initially

```shell
 docker run --mount type=bind,source="$(pwd)"/test,target=/user/src/app/mntdir --name=purencool_db -d  -t purencool_db:latest 
```

Stop service 

```shell
 docker stop purencool_db
```

Start service again

```shell
docker start purencool_db
```

#### Environment Variables

* `VARIABLE_ONE` - A Description
* `ANOTHER_VAR` - More Description
* `YOU_GET_THE_IDEA` - And another

#### Volumes

* `/your/file/location` - File location

#### Useful File Locations

* `/some/special/script.sh` - List special scripts
  
* `/magic/dir` - And also directories

## Built With

* Docker version 19.03.13

## Find Us

* [GitHub](https://github.com/purencool/purencool-studio)
* [Purencool Digial](https://www.purencool.digital)
* [Docker image](https://hub.docker.com/repository/docker/purencool/purencool-db/general)

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. 

## Authors

* **Purencool** - *Initial work* - [Purencool Digital](https://purencool.digital)



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details.

## Acknowledgments

* Purencool team


### Build
For this to build you will need to do the following
1. config.js needs to be installed
2. run `docker build -t "purencool_db:latest" .`


### Development

The below commands we use commonly in the development of this docker image

#### Docker build commands


```
docker images
```
Completely delete any reference of purencool_db locally

```
docker stop purencool_db && \
docker rm  purencool_db && \
docker rmi -f purencool_db
```

To rebuild and test purencool_db locally

```
docker build -t "purencool_db:latest" . && \
docker images && \
docker run  -p 3306:3306  --mount type=bind,source="$(pwd)"/test,target=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=q --name=purencool_db -d  -t purencool_db:latest  && \
docker exec -it purencool_db  /bin/sh

```





##### Stop all docker ps

```
 docker stop $(docker ps -aq)
```


##### Removed all images that in a halted state 


```
 docker rm $(docker ps -aq)
```

##### Removed all dangling images

```
docker rmi $(docker images --quiet --filter "dangling=true")
```
