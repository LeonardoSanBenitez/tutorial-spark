# spark-tutorial

## Running spark locally

```
sudo docker pull jupyter/pyspark-notebook
sudo docker run -it --rm -p 8888:8888 -p 8123:8123 -v "${PWD}":/home/jovyan/work jupyter/pyspark-notebook
```

you can find more info about this image in their [dockerhub](https://hub.docker.com/r/jupyter/pyspark-notebook) or their [github](https://github.com/jupyter/docker-stacks/tree/main/pyspark-notebook)

## Customizing the container

if you just wanna learn spark, this is useless

but you will deploy spark-based software to production and you wanna have full control over it, this is probably the type of thing that you'll need to do

just go to the folder `customized-container` and execute:

```
docker-compose up
```

and go to the address `http://127.0.0.1:8888?token=c61a728d-f4e6-45f0-9bb6-65646801f994`

and you should be able to run the same notebooks as in the last part.



**Cautionary note:** the file `customized-container/.env` stores the token above. Usually this file is used to store secrets/keys/credentials, and thus it's ignored in the git repo (using the `.gitignore` file). For learning purposes, <u>I'm explicitly committing this file to the repository</u>. If you want to store real secrets using this repository as base, please take this into consideration.



**TODO:** this doest' work yet, haha. You can see that I choose a blank ubuntu as base image. You could choose other: the one we used in the first part (`jupyter/pyspark-notebook`), one specific for kubenetes spark operators (`FROM gcr.io/spark-operator/spark-py:v3.0.0`), or one of the many ones lying around in the internet (like from [here](https://github.com/big-data-europe/docker-spark) or [here](https://github.com/bitnami/bitnami-docker-spark))

## Using a managed platform

other production-ready way of executing spark job is to use a managed platform, like AWS EMR or Databricks

TODO