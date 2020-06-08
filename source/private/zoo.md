

#### chooseOne 
* 两个 可用 非轮询


###  path 监听

NettyClientFactory.get().removeClient(cacheKey, client);

1. path 监听
    * 2020-05-25 11:00:01.486 INFO  [ZkClient-EventThread-11-172.17.202.101:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers, currentChilds :  [consumer%3A%2F%2F172.17.202.101%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590375599812%26version%3D0.2.1-SNAPSHOT%26weight%3D1]

    * 2020-05-25 10:59:58.119 ERROR [client-15]com.chaboshi.crpc.client.netty.NettyClient(67) | Client connect server(172.17.202.101:12030) fail !
  io.netty.channel.AbstractChannel$AnnotatedConnectException: Connection refused: /172.17.202.101:12030
  	at sun.nio.ch.SocketChannelImpl.checkConnect(Native Method)
  	at sun.nio.ch.SocketChannelImpl.finishConnect(SocketChannelImpl.java:717)
  	at io.netty.channel.socket.nio.NioSocketChannel.doFinishConnect(NioSocketChannel.java:346)
  	at io.netty.channel.nio.AbstractNioChannel$AbstractNioUnsafe.finishConnect(AbstractNioChannel.java:340)
  	at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:639)
  	at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:574)
  	at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:488)
  	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:450)
  	at io.netty.util.concurrent.SingleThreadEventExecutor$5.run(SingleThreadEventExecutor.java:873)
  	at java.lang.Thread.run(Thread.java:745)
  2020-05-25 11:00:01.122 INFO  [client-16]com.chaboshi.crpc.client.factory.AbstractClientFactory(156) | addClient success, serviceName:messageservice, client : NettyClient [cacheKey=messageservice, host=172.17.202.101, port=12030, connectTimeout=10000, idleCount=0]
  2020-05-25 11:00:01.122 INFO  [client-16]com.chaboshi.crpc.client.netty.NettyClient(65) | Client connect server(172.17.202.101:12030) success !
  2020-05-25 11:05:57.286 INFO  [worker-6]com.chaboshi.crpc.server.netty.NettyServerHandler(52) | channel register from /172.17.202.113:53183

### unregist



ice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590474472000%26version%3D0.2.1-SNAPSHOT%26weight%3D1, currentChilds :  []
2020-05-26 16:55:13.675 INFO  [ZkClient-EventThread-11-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/providers, currentChilds :  [crpc%3A%2F%2F172.17.202.101%3A12030%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590388397599%26version%3D0.2.1-SNAPSHOT%26weight%3D1, crpc%3A%2F%2F172.17.202.128%3A12030%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590474472000%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
2020-05-26 16:55:13.882 INFO  [worker-7]com.chaboshi.crpc.server.netty.NettyServerHandler(52) | channel register from /172.17.202.113:50942
2020-05-26 16:56:06.198 INFO  [server-33]com.chaboshi.scf.messageservice.impl.MessageService(119) | toAddress:sunyinlong@chaboshi.cn
2020-05-26 17:03:40.439 INFO  [worker-8]com.chaboshi.crpc.server.netty.NettyServerHandler(52) | channel register from /172.17.202.113:60490
2020-05-26 17:04:03.057 INFO  [worker-1]com.chaboshi.crpc.server.netty.NettyServerHandler(52) | channel register from /172.17.202.113:61569
2020-05-26 17:06:01.340 INFO  [SIGTERM handler]com.chaboshi.crpc.server.signal.ServerSignalHandler(25) | receive a signal named SIGTERM, so close the server now !
2020-05-26 17:06:01.340 WARN  [SIGTERM handler]com.chaboshi.crpc.server.netty.NettyServer(75) | Server stopped! serverConfig : ServerConfig [name=messageservice, host=172.17.202.128, address=tcp://172.17.202.128:12030, port=12030, protocol=tcp, worker=64, basepackages=[com.chaboshi.scf.messageservice], filters=[]]


2. 服务关闭 unregist


providers
2020-05-25 10:17:38.437 INFO  [pool-1-thread-7]com.chaboshi.scf.messageservice.impl.MessageService(100) | 成功
2020-05-25 11:13:41.491 INFO  [SIGTERM handler]com.chaboshi.crpc.server.signal.ServerSignalHandler(25) | receive a signal named SIGTERM, so close the server now !
2020-05-25 11:13:41.491 WARN  [SIGTERM handler]com.chaboshi.crpc.server.netty.NettyServer(75) | Server stopped! serverConfig : ServerConfig [name=messageservice, host=172.17.202.128, address=tcp://172.17.202.128:12030, port=12030, protocol=tcp, worker=64, basepackages=[com.chaboshi.scf.messageservice], filters=[]]
2020-05-25 11:13:41.496 WARN  [io-5]io.netty.channel.AbstractChannelHandlerContext(151) | Failed to submit an exceptionCaught() event.
java.util.concurrent.RejectedExecutionException: event executor terminated

[zk: localhost:2181(CONNECTED) 7] ls /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers
[consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590027674468%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
[zk: localhost:2181(CONNECTED) 8] ls /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/providers
[]

1. consummers
2020-05-25 11:21:21.607 ERROR [client-6]com.chaboshi.crpc.client.netty.NettyClient(67) | Client connect server(172.17.202.128:12030) fail !
io.netty.channel.AbstractChannel$AnnotatedConnectException: Connection refused: /172.17.202.128:12030
	at sun.nio.ch.SocketChannelImpl.checkConnect(Native Method)
	at sun.nio.ch.SocketChannelImpl.finishConnect(SocketChannelImpl.java:717)
	at io.netty.channel.socket.nio.NioSocketChannel.doFinishConnect(NioSocketChannel.java:346)
	at io.netty.channel.nio.AbstractNioChannel$AbstractNioUnsafe.finishConnect(AbstractNioChannel.java:340)
	at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:639)
	at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:574)
	at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:488)
	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:450)
	at io.netty.util.concurrent.SingleThreadEventExecutor$5.run(SingleThreadEventExecutor.java:873)
	at java.lang.Thread.run(Thread.java:745)


#### addRegist 
1. consumers
2020-05-25 11:18:02.742 ERROR [client-14]com.chaboshi.crpc.client.netty.NettyClient(67) | Client connect server(172.17.202.128:12030) fail !
io.netty.channel.AbstractChannel$AnnotatedConnectException: Connection refused: /172.17.202.128:12030
	at sun.nio.ch.SocketChannelImpl.checkConnect(Native Method)
	at sun.nio.ch.SocketChannelImpl.finishConnect(SocketChannelImpl.java:717)
	at io.netty.channel.socket.nio.NioSocketChannel.doFinishConnect(NioSocketChannel.java:346)
	at io.netty.channel.nio.AbstractNioChannel$AbstractNioUnsafe.finishConnect(AbstractNioChannel.java:340)
	at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:639)
	at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:574)
	at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:488)
	at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:450)
	at io.netty.util.concurrent.SingleThreadEventExecutor$5.run(SingleThreadEventExecutor.java:873)
	at java.lang.Thread.run(Thread.java:745)
2020-05-25 11:18:04.654 INFO  [ZkClient-EventThread-37-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/providers, currentChilds :  [crpc%3A%2F%2F172.17.202.128%3A12030%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590376684637%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
2020-05-25 11:18:04.672 INFO  [ZkClient-EventThread-37-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers, currentChilds :  [consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590027674468%26version%3D0.2.1-SNAPSHOT%26weight%3D1, consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590376684637%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
2020-05-25 11:18:05.744 INFO  [client-15]com.chaboshi.crpc.client.factory.AbstractClientFactory(156) | addClient success, serviceName:messageservice, client : NettyClient [cacheKey=messageservice, host=172.17.202.128, port=12030, connectTimeout=3000, idleCount=0]
2020-05-25 11:18:05.744 INFO  [client-15]com.chaboshi.crpc.client.netty.NettyClient(65) | Client connect server(172.17.202.128:12030) success !


#### 心跳 消费
[05-25 15:53:59,326 INFO ] [main-EventThread] I0Itec.zkclient.ZkClient[713] - zookeeper state changed (SyncConnected)
[05-25 15:53:59,326 DEBUG] [main-EventThread] I0Itec.zkclient.ZkClient[659] - Leaving process event
[05-25 15:53:59,326 DEBUG] [main] I0Itec.zkclient.ZkClient[950] - State is SyncConnected
[05-25 15:53:59,342 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 1,3  replyHeader:: 1,18361,0  request:: '/crpc,F  response:: s{18196,18196,1589954991510,1589954991510,0,5,0,0,0,1,18254} 
[05-25 15:53:59,400 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 2,8  replyHeader:: 2,18361,0  request:: '/crpc,F  response:: v{'com.chaboshi.scf.messageservice.contract.IMessageService} 
[05-25 15:53:59,460 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 3,8  replyHeader:: 3,18361,0  request:: '/crpc,F  response:: v{'com.chaboshi.scf.messageservice.contract.IMessageService} 
[05-25 15:53:59,492 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 4,8  replyHeader:: 4,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService,F  response:: v{'consumers,'providers} 
[05-25 15:53:59,551 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 5,8  replyHeader:: 5,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService,F  response:: v{'consumers,'providers} 
[05-25 15:53:59,617 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 6,8  replyHeader:: 6,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers,F  response:: v{'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590376684637%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377765401%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590378093652%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.101%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590388397599%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590389866293%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377666203%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590390035403%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1} 
[05-25 15:53:59,688 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 7,8  replyHeader:: 7,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers,F  response:: v{'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590376684637%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377765401%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590378093652%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.101%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590388397599%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590389866293%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377666203%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,'consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590390035403%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1} 
[05-25 15:53:59,748 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 8,8  replyHeader:: 8,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590376684637%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,F  response:: v{} 
[05-25 15:53:59,815 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 9,3  replyHeader:: 9,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590376684637%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: s{18291,18291,1590376684662,1590376684662,0,0,0,104013278127456870,0,0,18291} 
[05-25 15:53:59,877 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 10,8  replyHeader:: 10,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590376684637%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: v{} 
[05-25 15:53:59,936 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 11,8  replyHeader:: 11,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377765401%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,F  response:: v{} 
[05-25 15:53:59,996 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 12,3  replyHeader:: 12,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377765401%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: s{18302,18302,1590377765431,1590377765431,0,0,0,104013278127456870,0,0,18302} 
[05-25 15:54:00,055 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 13,8  replyHeader:: 13,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590377765401%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: v{} 
[05-25 15:54:00,118 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 14,8  replyHeader:: 14,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590378093652%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,F  response:: v{} 
[05-25 15:54:00,183 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 15,3  replyHeader:: 15,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590378093652%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: s{18310,18310,1590378093675,1590378093675,0,0,0,104013278127456870,0,0,18310} 
[05-25 15:54:00,240 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 16,8  replyHeader:: 16,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590378093652%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: v{} 
[05-25 15:54:00,297 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 17,8  replyHeader:: 17,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.101%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590388397599%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,F  response:: v{} 
[05-25 15:54:00,351 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 18,3  replyHeader:: 18,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.101%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590388397599%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: s{18313,18313,1590388397651,1590388397651,0,0,0,104013278127456870,0,0,18313} 
[05-25 15:54:00,412 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 19,8  replyHeader:: 19,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.101%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590388397599%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: v{} 
[05-25 15:54:00,474 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 20,8  replyHeader:: 20,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590389866293%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,F  response:: v{} 
[05-25 15:54:00,534 DEBUG] [main-SendThread(172.17.202.128:2181)] apache.zookeeper.ClientCnxn[843] - Reading reply sessionid:0x17187867eb60287, packet:: clientPath:null serverPath:null finished:false header:: 21,3  replyHeader:: 21,18361,0  request:: '/crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers/consumer%253A%252F%252F172.17.202.128%252Fcom.chaboshi.scf.messageservice.contract.IMessageService%253Fapplication%253Dmessageservice%2526serviceInterface%253Dcom.chaboshi.scf.messageservice.contract.IMessageService%2526side%253Dprovider%2526timestamp%253D1590389866293%2526version%253D0.2.1-SNAPSHOT%2526weight%253D1,T  response:: s{18325,18325,1590389866325,1590389866325,0,0,0,104013278127456870,0,0,18325} 
[05-25 15:54:00,589 DEBUG] [main-SendThread(172.17.202.128:2181)] apach

####  问题 消费者 重复 注册
1. 重启 messageservice 时， 重复 
2020-05-25 11:36:05.477 INFO  [ZkClient-EventThread-37-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/consumers, currentChilds :  [consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590027674468%26version%3D0.2.1-SNAPSHOT%26weight%3D1, consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590377018008%26version%3D0.2.1-SNAPSHOT%26weight%3D1, consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590376684637%26version%3D0.2.1-SNAPSHOT%26weight%3D1, consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590377765401%26version%3D0.2.1-SNAPSHOT%26weight%3D1, consumer%3A%2F%2F172.17.202.128%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590377666203%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
2020-05-25 11:36:05.739 INFO  [client-13]com.chaboshi.crpc.client.factory.AbstractClientFactory(156) | addClient success, serviceName:messageservice, client : NettyClient [cacheKey=messageservice, host=172.17.202.128, port=12030, connectTimeout=3000, idleCount=0]
2020-05-25 11:36:05.740 INFO  [client-13]com.chaboshi.crpc.client.netty.NettyClient(65) | Client connect server(172.17.202.128:12030) success !
2020-05-25 11:36:22.003 INFO  [ZkClient-EventThread-37-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/providers/crpc%3A%2F%2F172.17.202.128%3A12030%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590377666203%26version%3D0.2.1-SNAPSHOT%26weight%3D1, currentChilds :  null
2020-05-25 11:36:22.005 INFO  [ZkClient-EventThread-37-172.17.202.128:2181]com.chaboshi.crpc.registry.zookeeper.ZookeeperRegistry(211) | handleChildChange, parentPath : /crpc/com.chaboshi.scf.messageservice.contract.IMessageService/providers, currentChilds :  [crpc%3A%2F%2F172.17.202.128%3A12030%2Fcom.chaboshi.scf.messageservice.contract.IMessageService%3Fapplication%3Dmessageservice%26serviceInterface%3Dcom.chaboshi.scf.messageservice.contract.IMessageService%26side%3Dprovider%26timestamp%3D1590377765401%26version%3D0.2.1-SNAPSHOT%26weight%3D1]


#### 线上存在 zk节点 消失情况
[]
[zk: localhost:2181(CONNECTED) 2] ls /crpc/com.chaboshi.scf.userservice.contract.I

com.chaboshi.scf.userservice.contract.IProductPriceService       com.chaboshi.scf.userservice.contract.IAccountLogActionService   com.chaboshi.scf.userservice.contract.ILoginLogService           com.chaboshi.scf.userservice.contract.IUserDetailService         com.chaboshi.scf.userservice.contract.IUserService
com.chaboshi.scf.userservice.contract.IAccountLogService         com.chaboshi.scf.userservice.contract.IPerformanceService        com.chaboshi.scf.userservice.contract.IAccountSnapshotService    com.chaboshi.scf.userservice.contract.IAccountService            com.chaboshi.scf.userservice.contract.ICooperativeUserService
[zk: localhost:2181(CONNECTED) 2] ls /crpc/com.chaboshi.scf.userservice.contract.IAccount

com.chaboshi.scf.userservice.contract.IAccountLogActionService   com.chaboshi.scf.userservice.contract.IAccountLogService         com.chaboshi.scf.userservice.contract.IAccountSnapshotService    com.chaboshi.scf.userservice.contract.IAccountService
[zk: localhost:2181(CONNECTED) 2] ls /crpc/com.chaboshi.scf.userservice.contract.IAccountLog

com.chaboshi.scf.userservice.contract.IAccountLogActionService   com.chaboshi.scf.userservice.contract.IAccountLogService
[zk: localhost:2181(CONNECTED) 2] ls /crpc/com.chaboshi.scf.userservice.contract.IAccountLogService/

consumers   providers
[zk: localhost:2181(CONNECTED) 2] ls /crpc/com.chaboshi.scf.userservice.contract.IAccountLogService/providers
[]
[zk: localhost:2181(CONNECTED) 3] ls /crpc/com.chaboshi.scf.userservice.contract.IAccountLogService/consumers
[consumer%3A%2F%2F172.17.202.107%2Fcom.chaboshi.scf.userservice.contract.IAccountLogService%3Fapplication%3Duserservice%26serviceInterface%3Dcom.chaboshi.scf.userservice.contract.IAccountLogService%26side%3Dprovider%26timestamp%3D1585310205480%26version%3D0.2.1-SNAPSHOT%26weight%3D1]
[zk: localhost:2181(CONNECTED) 4]

               	<service name="messageservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
               		<registry address="zookeeper://172.17.202.101:2181" />
               	</service>
               	
               		<service name="messageservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
                
                		<registry address="zookeeper://172.17.202.128:2181" />
                		<!-- <server address="tcp://172.17.202.128:12030" /> -->
                	</service>
                	
                		<server name="messageservice" address="tcp://172.17.202.128:12030">
                    		<registry address="zookeeper://172.17.202.128:2181" />
                    		<scan basepackage="com.chaboshi.scf.messageservice" />
                    	</server>
                	
-- 配置
<service name="activityservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="agentservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="analysisservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="baseservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="basicservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="cacheservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="callbackservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="captchaservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="carinfoappraise" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="commonservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="companyservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="detectionservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="deviceservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="maintenanceservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="messageservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="middleservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="pushservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="reportservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="skuservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="userservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="valuationservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="vinservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

<service name="warrantyservice" codec="HESSIAN_CODEC" timeout="3000" loadbalance="ROUND_ROBIN">
    <registry address="zookeeper://172.17.202.101:2181" />
</service>

#### 测试计划
1. 101 配置更改
2. 101 crpc jar 包 替换
3. 部署 临时镜像环境, jekins 添加 新机器
    * baseservice
    * commonservice
    * reportservice
    * userservice
    * skuservice
4. 重启 crpc 测试观察
5. web 层 更改依赖，crpc 0.2.3，更改配置
6. 测试观察 


#### items  
1. 101 messageservice crpc.xml 配置 zk 修改