My-Notes
========
How to build a distributed microservices architecture based on Sagas. I am following the book named Microservices Patterns.

https://livebook.manning.com/#!/book/microservice-patterns/chapter-4/v-8/89

There are two ways of building this saga architectures, choreography and orchestrated.
A choreagrapher is basically a central object able to talk with differents services allocated in differents containers.

An Orchestra is basically the abbility that every service have in order to talk with different services.

https://stackoverflow.com/questions/4127241/orchestration-vs-choreography

21 March 2018
Added an xml graph showing how a choreography saga object should work. 

A central object talking with differents services allocated in different docker containers. I think that this object should be based on Tram framework with any producer consumer paradigm, in this case, if i want to talk with serviceA, i have to push a command with the request within TopicA and retrieve the response from ServiceA. When i have that response, i can push another request to ServiceB and wait for the response, and so on, so forth. Doing this way, i can guarantee global consistency because, because if i do not receive the response in a proper time, i can send a command to the previous services in order to going back to previuos state.

	https://github.com/eventuate-tram/eventuate-tram-sagas

7 Junio 2018

	https://kafka.apache.org/documentation.html#uses

para arrancar cassandra

	$:bin aironman$ cassandra -f

para arrancar nexus

	/usr/local/opt/nexus/libexec 

para saber los puertos abiertos por algun programa
	lsof -i -P | grep -i listen 

para saber los pid de los procesos java:

	ps -ef | grep java | grep awk ‘{print $2}’

arrancar/parar postgres
	lunchy start postgres

	lunchy stop postgres

donde esta la ISS?

	https://api.wheretheiss.at/v1/satellites/25544 pregunta cada segundo incluso

para sacar el certificado de un site
	
	openssl s_client -connect api.wheretheiss.at:443 -showcerts -prexit

para importar el certificado que me he bajado del anterior site
	
	keytool -import -alias iss -file iss.pem -keystore trust.jksº

clasificando documentos 

	http://chimpler.wordpress.com/2014/06/11/classifiying-documents-using-naive-bayes-on-apache-spark-mllib/

ficheros con fotos de Andromeda

	http://archive.stsci.edu/prepds/phat/datalist.html

descargarme video de youtube:

	youtube-dl https://www.youtube.com/watch?v=0KXME_y-3QA

arrancar solr

	solr

To have launchd start solr now and restart at login:
	brew services start solr
Or, if you don't want/need a background service you can just run:
solr start

levantar hdfs a lo bruto

	for x in `cd /etc/init.d ; ls hadoop-hdfs-*` ; do sudo service $x start ; done

levantar spark a lo bruto
	
	for x in `cd /etc/init.d ; ls spark-*` ; do sudo service $x start ; done

levantar zookeeper:

	zkServer start

levantar kafka:

	kafka-server-start /usr/local/etc/kafka/server.properties

levantar zookeeper

	zkServer start

levantar kafka

	kafka-server-start /usr/local/etc/kafka/server.properties

levantar instancia redis

	redis-server /usr/local/etc/redis.conf

levantar todos los servicios que tenga bajo init.d
	
	for x in `cd /etc/init.d ; ls hive-*` ; do sudo service $x start ; done

levantar impala a lo bruto:

	for x in `cd /etc/init.d ; ls impala-*` ; do sudo service $x start ; done



