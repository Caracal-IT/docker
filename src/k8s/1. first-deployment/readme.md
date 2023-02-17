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
   ```

7. qwqwe