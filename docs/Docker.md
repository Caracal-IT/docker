# <font color="#2EA3F2">Docker</font>
Docker is a software platform that allows you to build, test, and deploy applications quickly.

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



| Name                | Description                              | Command                     |
| ---                 | -----------                              |----                         |
| **Node Runr**       | Run a NodeJs server in interactive mode  | `docker run -it node`       |
