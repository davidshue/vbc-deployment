For the first time, do in the following sequence

kubectl apply -f Ingres-role.yaml
kubectl apply -f DeployDefaultBackend.yaml
kubectl apply -f DeployIngressController.yaml
kubectl apply -f DeployServiceIngressService.yaml
Go to azure console to configure the DNS of the 2 public IPs
kubectl apply -f DeployIngress.yaml