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

and you should be able to run the same notebooks as in the last part

TODO: I'm not sure if that container works, haha

## Using a managed platform

other production-ready way of executing spark job is to use a managed platform, like AWS EMR or Databricks

TODO