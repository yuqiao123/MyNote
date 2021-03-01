## Mac 安装 mongodb

### 1 下载安装包

下载地址：https://www.mongodb.com/try/download/community

![image](https://user-images.githubusercontent.com/34055414/109529460-b9a0e080-7af0-11eb-8b21-92f84f1561b0.png)



### 2 将tar文件解压

将解压后的文件移动到   /usr/local 文件夹下

将解压文件改称为MongoDB
![image](https://user-images.githubusercontent.com/34055414/109530283-7f840e80-7af1-11eb-8200-dd2ba807d16e.png)


### 3配置环境变量

```shell
sudo vim ~/.bash_profile
```

加入：export PATH=${PATH}:/usr/local/MongoDB/bin
![image](https://user-images.githubusercontent.com/34055414/109530350-93c80b80-7af1-11eb-81a1-49161f5bda0b.png)


### 4、根目录下新建 /data/db文件夹

```shell
sudo mkdir -p /data/db
```



### 5、启动 mongo 服务

终端输入

```shell
>>>mongod
```

```shell
2020-08-07T21:21:18.812+0800 I  CONTROL  [main] Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'
2020-08-07T21:21:18.823+0800 W  ASIO     [main] No TransportLayer configured during NetworkInterface startup
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] MongoDB starting : pid=53147 port=27017 dbpath=/data/db 64-bit host=192.168.0.100
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] db version v4.2.8
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] git version: 43d25964249164d76d5e04dd6cf38f6111e21f5f
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] allocator: system
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] modules: none
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] build environment:
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten]     distarch: x86_64
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten]     target_arch: x86_64
2020-08-07T21:21:18.827+0800 I  CONTROL  [initandlisten] options: {}
2020-08-07T21:21:18.832+0800 I  STORAGE  [initandlisten] Detected data files in /data/db created by the 'wiredTiger' storage engine, so setting the active storage engine to 'wiredTiger'.
2020-08-07T21:21:18.832+0800 I  STORAGE  [initandlisten] wiredtiger_open config: create,cache_size=3584M,cache_overflow=(file_max=0M),session_max=33000,eviction=(threads_min=4,threads_max=4),config_base=false,statistics=(fast),log=(enabled=true,archive=true,path=journal,compressor=snappy),file_manager=(close_idle_time=100000,close_scan_interval=10,close_handle_minimum=250),statistics_log=(wait=0),verbose=[recovery_progress,checkpoint_progress],
2020-08-07T21:21:19.295+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:295946][53147:0x10a6ec5c0], txn-recover: Recovering log 1 through 2
2020-08-07T21:21:19.357+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:357355][53147:0x10a6ec5c0], txn-recover: Recovering log 2 through 2
2020-08-07T21:21:19.421+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:421064][53147:0x10a6ec5c0], txn-recover: Main recovery loop: starting at 1/23424 to 2/256
2020-08-07T21:21:19.502+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:502985][53147:0x10a6ec5c0], txn-recover: Recovering log 1 through 2
2020-08-07T21:21:19.556+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:556233][53147:0x10a6ec5c0], txn-recover: Recovering log 2 through 2
2020-08-07T21:21:19.601+0800 I  STORAGE  [initandlisten] WiredTiger message [1596806479:601385][53147:0x10a6ec5c0], txn-recover: Set global recovery timestamp: (0, 0)
2020-08-07T21:21:19.653+0800 I  RECOVERY [initandlisten] WiredTiger recoveryTimestamp. Ts: Timestamp(0, 0)
2020-08-07T21:21:19.663+0800 I  STORAGE  [initandlisten] Timestamp monitor starting
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] ** WARNING: Access control is not enabled for the database.
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          Read and write access to data and configuration is unrestricted.
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] ** WARNING: This server is bound to localhost.
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          Remote systems will be unable to connect to this server. 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          Start the server with --bind_ip <address> to specify which IP 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          addresses it should serve responses from, or with --bind_ip_all to
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          bind to all interfaces. If this behavior is desired, start the
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] **          server with --bind_ip 127.0.0.1 to disable this warning.
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] 
2020-08-07T21:21:19.664+0800 I  CONTROL  [initandlisten] ** WARNING: soft rlimits too low. Number of files is 256, should be at least 1000
2020-08-07T21:21:19.673+0800 I  SHARDING [initandlisten] Marking collection local.system.replset as collection version: <unsharded>
2020-08-07T21:21:19.681+0800 I  STORAGE  [initandlisten] Flow Control is enabled on this deployment.
2020-08-07T21:21:19.682+0800 I  SHARDING [initandlisten] Marking collection admin.system.roles as collection version: <unsharded>
2020-08-07T21:21:19.682+0800 I  SHARDING [initandlisten] Marking collection admin.system.version as collection version: <unsharded>
2020-08-07T21:21:19.687+0800 I  SHARDING [initandlisten] Marking collection local.startup_log as collection version: <unsharded>
2020-08-07T21:21:19.687+0800 I  FTDC     [initandlisten] Initializing full-time diagnostic data capture with directory '/data/db/diagnostic.data'
2020-08-07T21:21:19.690+0800 I  SHARDING [LogicalSessionCacheRefresh] Marking collection config.system.sessions as collection version: <unsharded>
2020-08-07T21:21:19.691+0800 I  SHARDING [LogicalSessionCacheReap] Marking collection config.transactions as collection version: <unsharded>
2020-08-07T21:21:19.691+0800 I  NETWORK  [listener] Listening on /tmp/mongodb-27017.sock
2020-08-07T21:21:19.691+0800 I  NETWORK  [listener] Listening on 127.0.0.1
2020-08-07T21:21:19.691+0800 I  NETWORK  [listener] waiting for connections on port 27017
2020-08-07T21:21:20.007+0800 I  SHARDING [ftdc] Marking collection local.oplog.rs as collection version: <unsharded>
```



### 6、使用

新开终端输入

```shell
mongo
```

![image](https://user-images.githubusercontent.com/34055414/109530410-a3dfeb00-7af1-11eb-88ae-6f03670a3b65.png)

