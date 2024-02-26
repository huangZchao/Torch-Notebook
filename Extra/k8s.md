# 创建kubernets
## 1. 初始化master节点
```
kubeadm init --apiserver-advertise-address $(hostname -i)
```

## 2. 初始化集群网络
```
kubectl apply -n kube-system -f ""
```

## 3. 启动新的实例作为网络节点
```
kubeadm join ....
```

## 4. 查看节点
```
kubectl get nodes  ### 获取物理节点信息
kubectl get pods   ### 获取虚拟节点信息
```

## 5. 应用配置
```
kubectl apply ...
```

# 概念
[link](https://lib.jimmysong.io/kubernetes-handbook/cluster/namespace/)

- Node
- Namespace，虚拟集群
- Label，附着在object（如Pod）上的键值对；
  - Label Selector，筛出object集合
  - node affinity & antiaffinity
- annotation
- taint和toleration，与affinity相反；