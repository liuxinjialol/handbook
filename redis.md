$ wget http://download.redis.io/releases/redis-4.0.6.tar.gz

$ tar xzf redis-4.0.6.tar.gz

$ cd redis-4.0.6

$ make

$ src/redis-server或$ src/redis-server  **/redis.conf

$redis-cli -h {host} -p {port}

#Creating a Redis Cluster using the create-cluster script

port 7000

cluster-enabled yes

cluster-config-file nodes.conf

cluster-node-timeout 5000

appendonly yes

$mkdir cluster-test

$cd cluster-test

$mkdir 7000 7001 7002 7003 7004 7005

$cd 7000

$../redis-server ./redis.conf

$gem install redis

执行前一定要放开linux防火墙端口

$./redis-trib.rb create --replicas 0 192.168.1.1:7000 192.168.1.2:7001 192.168.1.3:7002

$./redis-trib.rb create --replicas 1 192.168.1.1:7000 192.168.1.2:7001 192.168.1.3:7002 192.168.1.4:7003 192.168.1.5:7004 192.168.1.6:7005

$ redis-cli -c -p 7000
