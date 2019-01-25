Cluster Installation

1. Create Kubernetes Cluster in digital Ocean
2. Install Kubectl https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl
2. Wait until all nodes start
2. Download Kubernetes Config file
4. Copy file to $HOME/.kube/config
5. Test conection to kubernetes cluster
```bash
kubectl get nodes
```
3. Install metrics-server
```bash
git clone https://github.com/kubernetes-incubator/metrics-server
cp metrics-server-deployment.yaml metrics-server/deploy/1.8+/
cd metrics-server && kubectl create -f deploy/1.8+/
```

Create or Update
```bash
kubectl apply -f autoscaling.yaml
```

Delete
```bash
kubectl apply -f autoscaling.yaml
```

View autoscaling

In terminal 1:
```bash
watch kubectl get hpa
```

View deployments

In terminal 2:
```bash
watch kubectl get deployment php-apache
```

Increase load

In terminal 3:
```bash
kubectl run -i --tty load-generator --image=busybox /bin/sh
while true; do wget -q -O- http://php-apache.default.svc.cluster.local; done
```

Decrease load

In terminal 3:
```bash
type <Ctrl> + C.
```

View usage of nodes (servers)
```bash
kubectl top node
```