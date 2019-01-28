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