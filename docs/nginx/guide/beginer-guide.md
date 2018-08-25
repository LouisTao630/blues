# 初学者指导手册
一些基本的使用方法及概念
## 启动和停止操作
使用命令：
```shell
nginx -s signal
```
其中*signal*为：
- stop - fast shutdown
- quit - granceful shutdown
- reload - reloading the configuration file
- reopen - reopening the log files
