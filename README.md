# generic-n-tier-dockers 
Dockers for created and n-tier service

The idea is to setup deploy scripts for various multi-tiered application setups to speed up intial createion of n-tier services.

Starting with local docker deployed services for development and local testing and adding remote deployments and cloud deployments

## Adding example dockers
Create a new branch in this repo to start creating a new example.
Since we are setting this up on the same machine we should try to keep the exposed ports from overpapping.  The mapping is the local port to the docker port.

For the two-tier servers fill in the following info.  If you use the local deploy then you can keep them all running to test. 
LOCAL:DOCKER  server  
8080:80       NGINX   vanilla - static only
8081:80       apache  vanilla - static only
8082:80       tomcat  vanilla - static only
8083:80       glassfish vanilla - static only
