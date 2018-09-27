#停止所有的container，这样才能够删除其中的images：
docker stop $(docker ps -a -q)
#如果想要删除所有container的话再加一个指令：
docker rm $(docker ps -a -q)
docker rm -vf $(docker ps -a -q)
#查看当前有些什么images
docker images
#删除images，通过image的id来指定删除谁
docker rmi <image id>
#想要删除untagged images，也就是那些id为<None>的image的话可以用
docker rmi $(docker images | grep "^<none>" | awk "{print $3}")
#要删除全部image的话
docker rmi $(docker images -q)
#查看容器日志
docker logs -f <容器名orID>
#当需要把一台机器上的镜像迁移到另一台机器的时候，需要保存镜像
docker save <镜像名> > /home/save.tar
#加载镜像
docker load < /home/save.tar
#构建自己的镜像
docker build -t <镜像名> <Dockerfile路径>
#如Dockerfile在当前路径
docker build -t <镜像名> .

重新查看container的stdout
sudo docker attach <containerID>

docker inspect

docker inspect --format '{{ .NetworkSettings.IPAddress }}' <containerID>

mvn clean package docker:build

docker run  -d  -p 2181:2181 zookeeper

docker run -p 80:80 -v /Users/admin/vue-demo/dist:/etc/nginx/html -v /Users/admin/nginxconf/nginx.conf:/etc/nginx/nginx.conf  nginx

docker run --privileged=true -p 8080:8080 -v /Users/admin/webapps/ROOT:/usr/local/tomcat/webapps/ROOT  tomcat  

docker run -d —-net=host tomcat

docker stats <containerID  or  name>
  
yum list installed |grep docker

yum -y remove docker.x86_64

