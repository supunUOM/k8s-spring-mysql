# k8s-spring-mysql
deploy spring app with MySQL with kubernetes.

## 1. Build docker image
`docker build spring-mysql-app:1.0 .`

## 2. Start Secrets
`kubectl apply -f k8s-secret.yaml`

* ### Added all the credentials like usernames, password etc.
## 3. Start ConfigMaps
`kubectl apply -f k8s-configmap.yaml`
* ### Added configuration like db_url.
* ### Because it can use many components.

## 4. Apply Deployments
`kubectl apply -f k8s-deployment.yaml`
* ### This File included 
  * Deployment
  * DB service
  * spring-app-external service (**_Type: LoadBalancer_**)