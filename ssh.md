本机免密码

$ssh-keygen -t rsa

$cd /root/.ssh

$cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

$chmod 0600 ~/.ssh/authorized_keys

$vi /etc/hosts

192.168.1.110 master

192.168.1.120 slave1

192.168.1.130 slave2

192.168.1.140 slave3

$hostname

ssh-copy-id slave1

ssh-copy-id slave2

ssh-copy-id slave3
