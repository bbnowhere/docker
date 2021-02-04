Downloading an Image
You can download a MariaDB image for Docker from the Offical MariaDB Repository, or choose another image that better suits your needs. You can search Docker Hub (the official set of repositories) for an image with this command:

 docker search mariadb
Once you have found an image that you want to use, you can download it via Docker. Some layers including necessary dependencies will be downloaded too. Note that, once a layer is downloaded for a certain image, Docker will not need to download it again for another image.

For example, if you want to install the default MariaDB image, you can type:

docker pull mariadb/server:10.4
This will install the 10.4 version. Versions 10.1, 10.2 and 10.3 are also valid choices.

You will see a list of necessary layers. For each layer, Dockers will say if it is already present, or its download progress.

To get a list of installed images:

docker images
Creating a Container
An image is not a running process; it is just the software needed to be launched. To run it, we must create a container first. The command needed to create a container can usually be found in the image documentation. For example, to create a container for the official MariaDB image:

### docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -d mariadb/server:10.3
mariadbtest is the name we want to assign the container. If we don't specify a name, an id will be automatically generated.

10.1 and 10.2 are also valid target versions:

### docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -d mariadb/server:10.1
### docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -d mariadb/server:10.2
Optionally, after the image name, we can specify some options for mysqld. For example:

# docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -d mariadb/server:10.3 --log-bin --binlog-format=MIXED
Docker will respond with the container's id. But, just to be sure that the container has been created and is running, we can get a list of running containers in this way:
