# Guestbook
```
[ ! -d 'guestbook' ] && git clone https://github.com/ibm-developer-skills-network/guestbook
export MY_NAMESPACE=sn-labs-$USERNAME
```

```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```

```
minikube delete
minikube start
minikube dashboard --url
```

```
ibmcloud plugin install container-registry
ibmcloud cr region-set global
ibmcloud cr namespace-list -v
ibmcloud cr image-list

ibmcloud cr login --client docker

```

```
kubectl create secret docker-registry ibm-cr-secret \
  --docker-server=us.icr.io \
  --docker-username=iamapikey \
  --docker-password=<YOUR_IAM_API_KEY> \
  --docker-email=<YOUR_EMAIL>
```

```
https://id.app.github.dev/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/#/workloads?namespace=default
```


```
kubectl apply -f deployment.yml
kubectl port-forward deployment.apps/guestbook 3000:3000
```


```
kubectl run -i --tty load-generator --rm --image=busybox:1.36.0 --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- https://animated-space-disco-q7p5xx5pqjqhxqjp-3000.app.github.dev/; done"
```



```
docker build . -t us.icr.io/h9g8723/guestbook:v1 && docker push us.icr.io/h9g8723/guestbook:v1
```
