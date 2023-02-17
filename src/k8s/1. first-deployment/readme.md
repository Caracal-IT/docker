# First App Deployment

This is a demonstaration on how to deploy a container to k8s.

## Steps

Follow the following steps to deply to k8s.

1. Check that MiniKube is running:

   ```code
    minikube status
   ```

2. Build your docker image.

    ```code
    docker build -t caracal/first-app:v1 .
    ```

3. Push your docker image.

    ```code
    docker push caracal/first-app:v1
    ```
  
4. Deploy the container to k8s.

    ```code
    kubectl create deployment first-app --image=caracal/first-app:v1
    ```

5. Check if the deployments was successful.

   ```code
   kubectl get deployments
   ```

6. Expose the IP Address (Service)
   
   ```code
   kubectl expose deployment first-app --type=LoadBalancer --port=8080 

   ```

   |Type|Description|
   |---|---|
   |ClusterIP|ip inside cluster|
   |NodePort|ip worker node|
   |LoadBalancer|external loadbalancer|

7. Check if service was created
   
   ```code
   kubectl get services
   ```
   
8. Get ip from minikube

    ```code
    minikube service first-app
    ```

9.  Add manual scalling (optional)
    
    ```code
    kubectl scale deployment/first-app --replicas=3 
    ```

10. Update deployment
    
    ```code
    kubectl set image deployment/first-app caracal/first-app:v1=caracal/first-app:v2
    ```

11. Check update status

    ```code
    kubectl rollout status deployment/first-app
    ```

12. wwwwww 



Notes:
Load Balancer
https://stackoverflow.com/questions/59412733/kubernetes-docker-desktop-with-multiple-loadbalancer-services
https://github.com/kubernetes-tn/guideline-kubernetes-enterprise/blob/master/general/desktop-env-setup.md