# MySQL
使用```StatefulSet```的```MySQL8```集群。

参考[运行一个有状态的应用程序](https://kubernetes.io/zh/docs/tasks/run-application/run-replicated-stateful-application/)

## 用法

```sh
$ kubectl create -f configmap.yml
$ kubectl create -f storageclass.yml
$ kubectl create -f service.yml
$ kubectl create -f statefulclass.yml
```