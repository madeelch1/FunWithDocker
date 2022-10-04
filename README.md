Commands:

Create a new network:

docker network create lbn

Create Containers (M1 and M2):

docker run -d -p 3000:80 -h M1 --net=lbn --name M1 m1
docker run -d -p 4000:80 -h M2 --net=lbn --name M2 m2

Create LB node
docker run -it -p 80:80 --net=M1 --name LB lb /bin/sh
