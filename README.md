# Script printing RAM and CPU utilization, disk partitions info and processes info

## Overview

Script **metrics** print RAM and CPU utilization, disk partitions info and processes info. The script accepts one or several arguments separated by spaces. These arguments instruct which metrics to print.
Available argument options:
- *ps* - to print info about processes
- *mem* - to print info about RAM and Swap usage
- *cpu* - to print info about CPU usage
- *disk* - to print info about partitions ans disk space usage

Wrong arguments are ignored.

## Argument usage examples

```bash
./metrics ps mem

./metrics cpu

./metrics ps cpu mem disk
```

## Prerequisites

In order to run this script you should have **Python 3** installed. You can get more information about Python 3 [at official website](https://docs.python.org/3/using/unix.html)
Also you should install **psutil library** according to this [guide](https://github.com/giampaolo/psutil/blob/master/INSTALL.rst)

If you want to try dockerized script you should have **Docker** installed. You can get more information about Docker installation [at official website](https://docs.docker.com/install/)

*Optional:* It's up to you whether you want to try running script via *docker-compose*. If so, you may read about *docker-compose* [installation](https://docs.docker.com/compose/install/)

## How to run this script

1. Download zip archive with source code from Github and unzip it or clone this repository using ```git clone```
YOu may need *git*. More information on *git* [here](https://git-scm.com/doc)
2. Go to folder *test_task_pro*
3. Run the script or Docker container from a command line with any available arguments: 
- script
```bash
./metrics ps mem
```
**OR**
- Docker container
```bash
./docker_run.sh ps mem
```
**OR**
- Docker container via *docker-compose*
```bash
docker-compose build
docker-compose run -e arguments="ps mem" metrics
```
4. *in case of using Docker:* Clean up - stop container, delete container and image. Also you may uncomment these lines at the end of *docker_run.sh* and omit this step.
```bash
docker stop test_task_lerkasan
docker rm test_task_lerkasan
docker rmi $(docker images | grep 'test_task_lerkasan')
```