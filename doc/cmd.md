1. Kubernetes クラスタコンポーネントの状態確認

```
$ kubectl get cs
NAME                 STATUS    MESSAGE              ERROR
scheduler            Healthy   ok                   
controller-manager   Healthy   ok                   
etcd-0               Healthy   {"health": "true"}   
```

2. Kubernetes Master の状態確認

```
$ kubectl cluster-info
Kubernetes master is running at http://localhost:8080

To further debug and diagnose cluster problems, use 'kubectl cluster-info dump'.
```

3. Kubernetes Node の状態確認

```
$ kubectl get nodes
NAME                    STATUS     AGE
127.0.0.1               NotReady   8d
node2                   Ready      6m
node3                   Ready      6m
```
4. Replication Controller の作成

```
$ kubectl run rc-nginx --image=nginx --replicas=2 --port=80
deployment "rc-nginx" created
```

5. Replication Controller の状態確認

```
$ kubectl get pods
```

6. Service の作成

```
$ kubectl expose rc rc-nginx --port=80 --type=LoadBalancer
```

7. Service の状態確認

```
$ kubectl get Service
```

9. Service の詳細確認

```
$ kubectl describe service rc-nginx
```
