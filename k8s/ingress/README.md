For the first time, do in the following sequence

kubectl apply -f Ingres-role.yaml
kubectl apply -f DeployDefaultBackend.yaml
kubectl apply -f DeployIngressController.yaml
kubectl apply -f DeployServiceIngressService.yaml
Go to azure console to configure the DNS of the 2 public IPs
kubectl apply -f DeployIngress.yaml


openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -out zenvault-stag-tls.crt \
    -keyout zenvault-stag-tls.key \
    -subj "/CN=zerodownkuber.eastus2.cloudapp.azure.com//O=zenvault-stag-tls"


kubectl create secret tls zenvault-stag-ingress-tls \
    --key zenvault-stag-tls.key \
    --cert zenvault-stag-tls.crt