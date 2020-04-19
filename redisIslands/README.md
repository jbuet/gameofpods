# Redis Islands

```bash
ssh node01 mkdir /redis0{1,2,3,4,5,6} # might not be necessary
kubectl apply -f .
kubectl exec -it redis-cluster-0 -- redis-cli --cluster create --cluster-replicas 1 $(kubectl get pods -l app=redis-cluster -o jsonpath='{range.items[*]}{.status.podIP}:6379 ')
```
