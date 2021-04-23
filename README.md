# tl;dr
https://github.com/RagingTiger/rpi_power_usage/blob/master/rpi4_power_usage.ipynb

# About
Repo for **JupyterLab** notebook for calculating **Raspberry Pi 4** power usage
stats.

# View On Github
Simply click:
https://github.com/RagingTiger/rpi_power_usage/blob/master/rpi4_power_usage.ipynb

# Usage
Below we will discuss running the `JupyterLab` server. 

## Docker
`Docker` will be the primary way discussed for running the `JupyterLab` server.
Please see the [Docker documentation](https://docs.docker.com/get-started/overview/)
for more info about `Docker`.

### Run
To get started simply pull down the repo and `cd` into the `rpi_power_usage`
directory:
```
$ git clone https://github.com/RagingTiger/rpi_power_usage
$ cd rpi_power_usage/
```
Next execute the following docker command while in the `rpi_power_usage` repo:
```
docker run -d \
           --rm \
           --name jupyter \
           -e JUPYTER_TOKEN=ragingtiger \
           -e JUPYTER_ENABLE_LAB=yes \
           -p 8888:8888 \
           -v $PWD:/home/jovyan/work \
           jupyter/base-notebook
```
NOTE: We used the `jupyter/base-notebook` **Docker image** here, but there are
many possible
[Jupyter Docker stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)
to choose from depending on how much pre-installed `Python libraries` you may
want to use with this `JupyterLab notebook`.

Now navigate to this **URL**
http://127.0.0.1:8888/lab/tree/work/rpi4_power_usage.ipynb?token=ragingtiger to
start using the `JupyterLab notebook`.

### Remove
To remove the server simply stop it
```
$ docker stop jupyter
```
