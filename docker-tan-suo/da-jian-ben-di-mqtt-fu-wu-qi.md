# 🚍 搭建本地MQTT服务器

使用Docker容器来搭建一个本地的MQTT服务器

1.创建相关文件夹&#x20;

`mkdir -p /mnt/mmcblk2p4/docker/mqtt/config`&#x20;

`mkdir -p /mnt/mmcblk2p4/docker/mqtt/data`&#x20;

`mkdir -p /mnt/mmcblk2p4/docker/mqtt/log`&#x20;

增加配置文件&#x20;

nano /mnt/mmcblk2p4/docker/mqtt/config/mosquitto.conf&#x20;

复制以下内容：&#x20;

persistence true persistence\_location /mosquitto/data log\_dest file /mosquitto/log/mosquitto.log listener 1883 allow\_anonymous false password\_file /mosquitto/config/pwfile.conf

保存退出。 运行容器命令：

&#x20;`docker run -it --name=mosquitto --privileged -p 1883:1883 -p 9001:9001 -v /mnt/mmcblk2p4/docker/mqtt/config/mosquitto.conf:/mosquitto/config/mosquitto.conf -v /mnt/mmcblk2p4/docker/mqtt/data:/mosquitto/data -v /mnt/mmcblk2p4/docker/mqtt/log:/mosquitto/log -d eclipse-mosquitto`&#x20;

docker ps&#x20;

找到容器id&#x20;

docker exec -it id sh&#x20;

运行命令 mosquitto\_passwd /mosquitto/config/pwfile.conf mqtt&#x20;

创建用户和密码 ctrl+p，ctrl+q。 重启容器 docker restart id
