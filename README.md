# generic-n-tier-dockers 
Dockers for created and n-tier service

The idea is to setup deploy scripts for various multi-tiered application setups to speed up intial creation of n-tier services.

Starting with local docker deployed services for development and local testing and adding remote deployments and cloud deployments

## Adding example dockers

Create a new branch in this repo to start creating a new example.
Since we are setting this up on the same machine we should try to keep the exposed ports from overpapping.  The mapping is the local port to the docker port.

The idea is that you can cd to the directory of the docker you wish do deploy and run the command: docker-compose up --build
to build and deploy the docker image.  Please note that in the future the builds may fail if the docker base images move.


### Static only dockers 
For the two-tier servers fill in the following info.  If you use the local deploy then you can keep them all running to test. 
| LOCAL:DOCKER | server |  Start URL |
| --- | --- | --- |
| 8080:80 | NGINX  - static only | http://localhost:8080 |
| 8081:80 | apache  - static only | http://localhost:8081 |
| 8888:8080 | tomcat - static only | http://localhost:8888/static |
| 8083:80 | openresty - satic only | http://localhost:8083 |

