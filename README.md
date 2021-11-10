# generic-n-tier-dockers 
Dockers for created and n-tier service

The idea is to setup deploy scripts for various multi-tiered application setups to speed up intial creation of n-tier services.

Starting with local docker deployed services for development and local testing and adding remote deployments and cloud deployments

## Adding example dockers

Create a new branch in this repo to start creating a new example.
Since we are setting this up on the same machine we should try to keep the exposed ports from overlapping.  The mapping is the local port to the docker port.

The idea is that you can cd to the directory of the docker you wish do deploy and run the command: docker-compose up --build
to build and deploy the docker image.  Please note that in the future the builds may fail if the docker base images move.


### 2-tier Dockers

A 2-tier application is implementing a client/server model webservice.  The client tier consists of a process on the requestors machine and is usually a webrowser.  The server tier is a process that listens for requests and returns a result to the requestor.  The server is can be listening to a tcp or udp socket. Most web servers are implementing the http protocol and therefor listening on an tcp port for an http request.

#### static-only server dockers
The idea of a static only server is to provide content that does not change by the processing of a request.  The content may change in the future and may need to have the local caches on the client side cleared inorder for the new content to be retrieved.

For the two-tier static only server port numbers are assigned below so that the local deploy can keep them all running to test. 
| LOCAL:DOCKER | server |  Start URL | Status |
| --- | --- | --- | --- |
| 8080:80 | NGINX  - static only | http://localhost:8080 | Implemented |
| 8081:80 | apache  - static only | http://localhost:8081 |  Implemented |
| 8083:80 | openresty - satic only | http://localhost:8083 |  Implemented |
| 8888:8080 | tomcat - static only | http://localhost:8888/static |  Implemented |


#### application servers
The focus is on servers that deliver dynamic content with and/or without a database.
| LOCAL:DOCKER | server |  Start URL | Status |
| --- | --- | --- | --- |
| 9080:80 | NGINX  -  applicaiton server | http://localhost:9080 | not implemented |
| 9081:80 | apache  - application server(CGI) | http://localhost:9081 |not implemented |
| 9083:80 | openresty - application server | http://localhost:9083 |not implemented |
| 9888:8080 | tomcat - application server | http://localhost:9888/ |not implemented |
| 9889:8080 | ruby - application server | http://localhost:9889/ |not implemented |

