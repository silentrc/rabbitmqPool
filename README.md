来源 
https://github.com/Braveheart7854/rabbitmqPool
添加了exchangeType

# 依赖包
github.com/streadway/amqp

# 开始使用
```
go get github.com/silentrc/rabbitmqPool
```

- 代码如下 
```	
rabbitmqPool.AmqpServer = rabbitmqPool.Service{
	AmqpUrl:"amqp://guest:guest@localhost:5672/",
	ConnectionNum:10,
	ChannelNum:100,
}

rabbitmqPool.InitAmqp()	

message,err := rabbitmqPool.AmqpServer.PutIntoQueue(ExchangeName,ExchangeType,RouteKey,data)
if err != nil{
	//若有错误，则表示消息发送失败，做好失败消息处理
	rabbitmqPool.Logger.Notice(message)
}
```