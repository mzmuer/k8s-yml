# MySQL
使用```StatefulSet```的```Redis```集群。

## 用法

```sh
$ kubectl create -f configmap.yml
$ kubectl create -f storageclass.yml
$ kubectl create -f service.yml
$ kubectl create -f statefulclass.yml
```

## 集群的节点的添加和主从切换

首先上面只是启动了6个redis节点，

### 构建集群

方法一：进入任意一个pod执行下面命令
```sh
redis-cli --cluster create 10.1.0.157:6379 10.1.0.158:6379 10.1.0.159:6379 10.1.0.160:6379 10.1.0.161:6379 10.1.0.162:6379 --cluster-replicas 1
```
但是不方便扩展。和pod挂掉后主从切换。

方法二：再启动一个pod运行redis-trib来管理集群。方便主从切换和节点扩展。