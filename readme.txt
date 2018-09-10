========================================================================================
>>> CITIC BIB Phase 1.0 Beginning of Oct 2018
========================================================================================
>>> 
========================================================================================

git clone --depth=1 https://github.com/oracle/docker-images.git


docker images/OracleJava/Java-8

build.sh


docker images

docker run -it --name java8test container-registry.oracle.com/java/serverjre:8 bash



docker run -it --name weblogic_bash container-registry.oracle.com/middleware/weblogic:latest bash

echo "username=weblogic" >> domain.properties
echo "password=welcome1" >> domain.properties

docker commit {docker id}

docker exec -t weblogic_bash cat domain.properties


docker run -d -p 7001:7001 -p 9002:9002  -v $PWD/domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:12.2.1.3

create your local domain.properties
username=weblogic
password=welcome1


docker run -d -p 7001:7001 -p 9002:9002  -v domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:12.2.1.3

docker run -d -p 7001:7001 -p 9002:9002  -v domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest


docker run -d -p 7002:7001 -p 9002:9002  -v domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest

https://localhost:9002/console


docker run -it –name WebLogic /bin/bash/

docker run -d --name wlsadmin --hostname wlsadmin -p 7001:7001 --env-file ./container-scripts/domain.properties -e ADMIN_PASSWORD=welcome1 -v <host directory>:/u01/oracle/user_projects 12213-domain

docker run -d --name MS1 --link wlsadmin:wlsadmin -p 8001:8001 --env-file ./container-scripts/domain.properties -e ADMIN_PASSWORD=welcome1 -e MS_NAME=MS1 --volumes-from wlsadmin 12213-domain createServer.sh




docker pull -a  radudobrinescu/wls12c ===> all version to be pull from docker store

docker pull radudobrinescu/wls12c:latest
docker run -itd -e SERVER_TYPE=AdminServer –-name AdminServer –expose=7001 -p 7001:7001 radudobrinescu/wls12c:1.0 bash -c “/oracle/fmwhome/wlst_custom/startWLS12c.sh && /bin/bash”




docker pull  container-registry.oracle.com/middleware/weblogic:latest

docker run -it --name weblogic_bash container-registry.oracle.com/middleware/weblogic:latest bash

echo "username=weblogic" >> \u01\oracle\properties\domain.properties
echo "password=welcome1" >> \u01\oracle\properties\domain.properties

exit

docker start weblogic_bash
docker attach weblogic_bash
docker commmit weblogic_bash


docker run -itd --name AdminServer -p 127.0.0.1:7001:7001 -p 127.0.0.1:9002:9002 -v c:\users\pettam\domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest

docker run -itd --name AdminServer -p 127.0.0.1:7001:7001 -p 127.0.0.1:9002:9002 -v c:\users\pettam\domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest



docker run -itd -e SERVER_TYPE=AdminServer --name AdminServer -p 7001:7001 -p 9002:9002 container-registry.oracle.com/middleware/weblogic:latest bash

docker run -itd -e SERVER_TYPE=AdminServer --name AdminServer -p 7001:7001 -p 9002:9002  -v domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest bash -c "/u01/orcle/createAndStartEmptyDomain.sh && /bin/bash"




docker run -itd -e SERVER_TYPE=AdminServer --name AdminServer -p 7001:7001 -p 9002:9002 container-registry.oracle.com/middleware/weblogic:latest bash -c "sh /u01/oracle/user_projects/domains/base_domain/startWebLogic.sh"

docker exec -t weblogic_bash cat domain.properties

docker run -it --name AdminServer -p 7001:7001 -p 9002:9002 container-registry.oracle.com/middleware/weblogic:latest bash -c "/u01/oracle/user_projects/domains/base_domain/startWebLogic.sh && /bin/bash"

docker exec -t weblogic_bash bash -c "/u01/oracle/user_projects/domains/base_domain/startWebLogic.sh && /bin/bash"


docker run -itd --name AdminServer -p 7001:7001 -p 9002:9002 -v domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest

docker run -itd --name AdminServer -p 10.0.75.1:7001:7001 -p 10.0.75.1:9002:9002 -v c:\users\pettam\domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest

docker run -itd --name AdminServer -p 7001:7001 -p 9002:9002 -v c:\users\pettam\domain.properties:/u01/oracle/properties/domain.properties container-registry.oracle.com/middleware/weblogic:latest






docker inspect --format='{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' AdminServer
172.17.0.2

10.0.75.1 


====================================================================
:: OS level hardening : Solaris + Weblogic Versioning to be aligned 
:: OS (version + apply latest batch)
====================================================================
:: init: not MO
:: after production: changed to MO
====================================================================
:: Priority : TESTING machines
:: Draft the milestone
====================================================================




        <wls:show-archived-real-path-enabled>true</wls:show-archived-real-path-enabled>    	




Please ensure Hyper-V is disabled in Windows Features, or refer to the Intel HAXM documentation for more information.

Hyper-V must be disabled for emulator 
HAXM for emulator 