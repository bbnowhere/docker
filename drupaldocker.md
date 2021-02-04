## In Your docker file write the below given lines 


FROM drupal:8.9.1


EXPOSE 80

## Build the images from the dockerfile using below command

docker build -t drupalserver .

## Check the images 

docker images 

## Create the container based on the image

docker run -tid -p 8083:80 --name=drupal8websites --link mariadbdockerimage:mysql -v /home/(name of your web directory):/var/www/html drupalserver

DONE
