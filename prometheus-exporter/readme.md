1. redis_exporter部署完后，需要修改/usr/lib/systemd/system/redis_exporter.service，加入redis密码和端口,然后执行systemctl start redis_exporter.service

2. mysql_exporter部署前，需要创建用户
   CREATE USER 'exporter'@'%' IDENTIFIED BY 'Export_12';
   GRANT PROCESS, REPLICATION CLIENT, SELECT ON *.* TO 'exporter'@'%';
   flush privileges;  

3. oracle_exporter部署完后，需要修改/usr/lib/systemd/system/oracle_exporter.service,将下面一行的账号密码和实例名添加进去，然后执行systemctl start oracle_exporter.service
   Environment=DATA_SOURCE_NAME="username/password@sid"

4.kafka mongodb  rabbitmq rocketmq redis已经验证成功  
