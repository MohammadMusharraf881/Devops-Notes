Docker Info

checking history:

shows the history of a docker image with the image name mentioned in the command
command: docker history httpd


Download image:
when we need to pull the docker image from docker hub

Images:
To list all the docker image pulled on the system

Run:
 The docker run command used to create and start a new container from a docker image. the basic syntax of the docker run is:

 docker run [options] IMAGE [COMMAND] [ARG]

 options:
  optional flag that configure the behaviour of the container, such as setting environment , variables mounting volumes, etc

    docker run httpd echo "Hello,World!"

Setting Environment

docker run -e MY_VAR=value httpd env

this command sets an enviornment variable 'MY_VAR' to the value "value" and runs a new container from the httpd image 

the 'env' command is used to display the list of environment variables in the container.