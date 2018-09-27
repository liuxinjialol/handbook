#更改limits限制

$vi /etc/security/limits.conf

* soft nofile 65536

* hard nofile 131072

$vi /etc/sysctl.conf 

添加下面配置：

vm.max_map_count=655360

并执行命令：

sysctl -p

firewalld的基本使用

启动： systemctl start firewalld

查看状态： systemctl status firewalld 

停止： systemctl disable firewalld

禁用： systemctl stop firewalld

启动一个服务：systemctl start firewalld.service

关闭一个服务：systemctl stop firewalld.service

重启一个服务：systemctl restart firewalld.service

显示一个服务的状态：systemctl status firewalld.service

在开机时启用一个服务：systemctl enable firewalld.service

在开机时禁用一个服务：systemctl disable firewalld.service

查看服务是否开机启动：systemctl is-enabled firewalld.service

查看已启动的服务列表：systemctl list-unit-files|grep enabled

查看启动失败的服务列表：systemctl --failed

那怎么开启一个端口呢

添加:firewall-cmd --zone=public --add-port=80/tcp --permanent    （--permanent永久生效，没有此参数重启后失效）与下面“重新载入”配合使用

重新载入:firewall-cmd --reload

查看:firewall-cmd --zone= public --query-port=80/tcp

删除:firewall-cmd --zone= public --remove-port=80/tcp --permanent

配置文件：/etc/firewalld/zones/public.xml

linux自定义ip地址

$/etc/sysconfig/network-scripts/ifcfg-xxx

linux环境变量

$/etc/profile
