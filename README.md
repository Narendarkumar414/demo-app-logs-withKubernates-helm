kubectl apply -f logstash.yml

kubectl apply -f deployment.yml
(exec into the pod and hit curl http://localhost for generating logs)

after that use helm for elasticsearch and kibana

helm install elasticsearch elastic/elasticsarch --set replicas=1

helm install kibana elastic/kibana --set service.type=LoadBalancer --set replicas=1

hit loadbalancer dns with portno. 5601 for kibana dashboard
