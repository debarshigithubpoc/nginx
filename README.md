STEPS

Download and install openssl
Create two ssl certificates self signed using openssl

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls/tls.key -out tls/tls.crt -subj "/CN=noelbansikah.dev"

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout tls/tls.key -out tls/tls.crt -subj "/CN=noelbansikah.com"

Install helm charts
-------------------

helm install ingress-nginx ./ingress-nginx 

helm install portfolio-dev . -f values-dev.yaml -n dev

helm install portfolio-staging . -f values-staging.yaml -n staging

set the ingress ip address on the host file

172.23.217.123	noelbansikah.dev
172.23.217.123	noelbansikah.com