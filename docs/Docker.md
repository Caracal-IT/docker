# <font color="#2EA3F2">Docker</font>
Docker is a software platform that allows you to build, test, and deploy applications quickly.

Play with Docker - https://labs.play-with-docker.com

Docker packages software into standardized units called containers that have everything the  
software needs to run including libraries, system tools, code, and runtime. 

Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

![Docker, the Docker mascot](assets/images/docker.png)

## <font color="#2EA3F2">Commands</font>

| Name                 | Description                                                 | Command                                              |
| ---                  | -----------                                                 |----                                                  |
| **Pull**             | Get image from docker hub                                   | `docker pull node`                                   |
| **Build**            | Build the image                                             | `docker build .`                                     |
| **Build With Name**  | Build the image with a name and tag                         | `docker build -t goals:latest .`                     |
| **Run**              | Run the image on port 3000                                  | `docker run -p 3000:3000 8a1c26431a`                 |
| **Run With Name**    | Run the image on port 3000 and set the name                 | `docker run -p 3000:3000 --name goalsapp 8a1c26431a` |
| **Run**              | Run the image on port 3000 detatched                        | `docker run -d -p 3000:3000 8a1c26431a`              |
| **List Containers**  | List the running containers                                 | `docker ps`                                          |
| **List Containers**  | List all the containers                                     | `docker ps -a`                                       |
| **Stop Container**   | Stop container 'vigorous_dirac'                             | `docker stop vigorous_dirac`                         |
| **Start Container**  | Restart container 'vigorous_dirac'                          | `docker start vigorous_dirac`                        |
| **Start Container**  | Restart container 'vigorous_dirac' attached                 | `docker start -a vigorous_dirac`                     |
| **Start Container**  | Restart container 'vigorous_dirac' attached interactive     | `docker start -a -i vigorous_dirac`                  |
| **Attach Container** | Attach to container 'vigorous_dirac'                        | `docker attach vigorous_dirac`                       |
| **Get Logs**         | Get logs from container 'vigorous_dirac'                    | `docker logs vigorous_dirac`                         |
| **Follow Logs**      | Listen for logs from container 'vigorous_dirac'             | `docker logs -f vigorous_dirac`                      |
| **Remove Container** | Remove a container that is not running                      | `docker rm vigorous_dirac`                           |
| **Remove Container** | Remove a container that is not running                      | `docker container prune`                             |
| **Auto Delete**      | Run the image on port 3000 and delete when stopped          | `docker run -p 3000:3000 --rm 8a1c2641a`             |
| **List Images**      | List the images                                             | `docker images`                                      |
| **Remove Images**    | Remove images                                               | `docker rmi 748384756`                               |
| **Remove Images**    | Remove images with no running containers                    | `docker image prune`                                 |
| **Inspect Info**     | Get more information about the image                        | `docker image inspect 8a1c2641a`                     |
| **Copy**             | Copy files from or into a running container                 | `docker cp dummy/. boring_vaughn:/test`              |
| **Publish**          | Publish image to Docker Hub                                 | `docker push caracal/springboot_api`                 |
| **Volume**           | Display the volumes                                         | `docker volume ls`                                   |
| **Named Volume**     | Create volume on client                                     | `docker run -p 3000:3000 -v feedback:app/fback 444a` |
| **Remove Volume**    | Remove volume on client                                     | `docker volume prune`                                |
| **Remove Volume**    | Remove volume on client                                     | `docker volume rm VOL_NAME`                          |
| **Bind Mount**       | Create volume on client                                     | `docker run -p 3000:3000 -v dir:app/fback 444a`      |
| **Add Network**      | Add a network to the container (Create network yourself)    | `docker run --network my_network`                    |
| **Create Network**   | Create a docker network                                     | `docker network create my_network`                   |


| Name                | Description                              | Command                     |
| ---                 | -----------                              |----                         |
| **Node Run**        | Run a NodeJs server in interactive mode  | `docker run -it node`       |
| **Access host ip**  | Call localhost from within the container | `host.docker.internal`      |

##  Resources

|Resource|Location|
|---|---|
|GitHub|https://github.com/bretfisher/udemy-docker-mastery|


https://headsigned.com/posts/mounting-docker-volumes-with-docker-toolbox-for-windows/


 install dashboard
 https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md
 https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/
 kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.6.1/aio/deploy/recommended.yaml

 kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

 run kubectl proxy to access dashboard
access dashboard
  http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/.