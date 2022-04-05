# druid命令

关闭服务

```
bin/service --down
```

启动服务

```
cd /opt/apache-druid-0.17.1
nohup /opt/apache-druid-0.17.1/bin/start-nano-quickstart &



```

druid测试环境配置：

```
Bootstrap servers:172.16.8.40:9092
topic:nginx170
{
  "bootstrap.servers": "172.16.8.40:9092"
}



kafka-console-consumer --bootstrap-server 172.16.8.122:9092 --from-beginning --topic OCEAN_GATEWAY_INTERFACE_STATISTICS_TOPIC

kafka-console-producer --broker-list 172.16.8.122:9092 --topic OCEAN_GATEWAY_INTERFACE_STATISTICS_TOPIC



耗时最大值，耗时最小值，耗时总时长

kafka-console-consumer --bootstrap-server 10.255.18.248:9092 --from-beginning --topic test6

bin/kafka-console-consumer.sh --bootstrap-server 192.168.1.44:9092,192.168.1.45:9092,192.168.1.47:9092,192.168.1.43:9092  --from-beginning --topic wxapplog_v3 --max-messages 10

 bin/kafka-consumer-groups.sh --bootstrap-server 192.168.1.44:9092,192.168.1.45:9092,192.168.1.47:9092,192.168.1.43:9092  --group test_search --describe 

bin/kafka-console-consumer.sh --bootstrap-server 
 192.168.1.34:9092 --from-beginning --topic test6 --max-messages 10

bin/kafka-console-producer.sh --broker-list 10.255.18.248:9092 --topic test6


```

```
druid.metadata.storage.type=mysql
druid.metadata.storage.connector.connectURI=jdbc:mysql://172.16.8.38:3306/test_druid
druid.metadata.storage.connector.user=test_druid
druid.metadata.storage.connector.password=test_druid123
mysql -h 172.16.8.38 -utest_druid -p
test_druid123

cd /opt/apache-druid-0.16.1-incubating/conf/druid/cluster

```



需要确认的问题：

- kafka的topic和Kafka的机器
- 采集的机器数量
- 采集的频率
- 采集的模块（app，服务器）
- replicas提供容错
- ~~druid时区问题~~
- ~~druid晚上挂掉(已经没有)~~
- ~~数据需要提前计算(响应时间)~~
- ~~case when 查询， 最大，最小~~



192.168.1.20    pro-middleware-druid-20
192.168.1.21    pro-middleware-druid-21
192.168.1.22    pro-middleware-druid-22
192.168.1.23    pro-middleware-druid-23

修改机器名字

```
hostnamectl set-hostname pro-middleware-druid-23
```

9楼打印机，配置未变，详情如下：

打印机地址：\\pc-print
登录账号：Guest
无密码