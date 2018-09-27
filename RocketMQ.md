nohup sh mqnamesrv &

nohup sh mqbroker -c $ROCKETMQ_HOME/conf/2m-noslave/broker-a.properties &

nohup sh mqbroker -c $ROCKETMQ_HOME/conf/2m-noslave/broker-b.properties &
