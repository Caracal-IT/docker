# <font color="#2EA3F2">Docker</font>
Docker is a software platform that allows you to build, test, and deploy applications quickly.

Docker packages software into standardized units called containers that have everything the  
software needs to run including libraries, system tools, code, and runtime. 

Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

![Docker, the Docker mascot](assets/images/docker.png)

## <font color="#2EA3F2">Commands</font>

| Name                | Description                     | Command                              |
| ---                 | -----------                     |----                                  |
| **Pull**            | Get image from docker hub       | `docker pull node`                   |
| **Build**           | Build the image                 | `docker build .`                     |
| **Run**             | Run the image on port 3000      | `docker run -p 3000:3000 8a1c26431a` |
| **List Containers** | List the running containers     | `docker ps`                          |
| **List Containers** | List all the containers         | `docker ps -a`                       |
| **Stop Container**  | Stop container 'vigorous_dirac' | `docker stop vigorous_dirac`         |

| Name                | Description                              | Command                     |
| ---                 | -----------                              |----                         |
| **Node Runr**       | Run a NodeJs server in interactive mode  | `dockerrun -it node`        |
