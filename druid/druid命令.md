# druid命令

关闭服务

```
bin/service --down
```

启动服务

```
cd /opt/apache-druid-0.17.1
nohup /opt/apache-druid-0.17.1/bin/start-nano-quickstart > log.log 2>&1 &



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

kafka-console-consumer --bootstrap-server 172.16.7.147:31123 --from-beginning --topic OCEAN_GATEWAY_INTERFACE_STATISTICS_TOPIC


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

