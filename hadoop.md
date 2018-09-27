1、配置1主3从，配置ssh认证登陆

$vi /etc/hosts

192.168.1.110 master

192.168.1.120 slave1

192.168.1.130 slave2

192.168.1.140 slave3

master免密码登陆

$ssh-keygen -t rsa

$cd /root/.ssh

$cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

$chmod 0600 ~/.ssh/authorized_keys

slave免密码登陆

ssh-copy-id slave1

ssh-copy-id slave2

ssh-copy-id slave3

2、配置hadoop

/etc/hadoop/hadoop-env.sh,添加

export JAVA_HOME=/usr/local/java/jdk8/

/etc/hadoop/core-site.xml,添加

<configuration>
    
<property>
    
    <name>fs.defaultFS</name>
    
    <value>hdfs://master:9000</value>
    
</property>

</configuration>

slaves,添加主机名(master上面slave1，slave2，slave3，slave上面为各自名字)

3、启动hadoop

master上面执行/sbin/start-all.sh
