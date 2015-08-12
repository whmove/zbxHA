zbxHA
=====

zabbix server high availability solutions, can be used to manage virtual IP and zabbix server process.


zbxha.conf
# 日志文件
[log]
logfile = /var/log/zbxlb.log

# zabbix 服务的虚IP、掩码、网关、虚IP启用的网卡、服务端口
[zbxservice]
serviceip = 10.8.104.29
netmask = 24
gateway = 10.8.104.254
device = bond0
zbxport = 10051

# zabbix 服务的主机，SSH连接方式
[zbxhost]
masterhost = 10.8.104.22
slavehost = 10.8.104.23
user = admin
pwd = 
port = 1022
sshkey = /etc/zbxha/id_rsa
failback = true

# zabbix 上添加用于测试zabbix服务状态是否可用的虚拟主机，添加一个 zabbix trapper 类型的item，设置其 key 为 hatest
[zbxsender]
hostname = zbxlb
key = hatest
value = 1
