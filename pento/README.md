# Pento

Fix apiservice and node01.

```bash
cp /etc/kubernetes/pki/ca.crt /etc/kubernetes/pki/ca-authority.crt

kubectl config set clusters.kubernetes.server https://172.17.0.46:6443

kubectl uncordon node01

kubectl patch deploy -n kube-system coredns -p '{"spec":{"template":{"spec":{"containers":[{"name":"coredns","image":"k8s.gcr.io/coredns:1.3.1"}]}}}}'
```

Apply kubernetes manifest `kubectl apply -f .`
