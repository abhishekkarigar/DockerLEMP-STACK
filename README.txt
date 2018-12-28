$ docker-compose up -d 
$ curl <docker-machine-ip>

$ curl <docker-machine-ip>:8183

	server = docker-machine ip (192.168.99.100)
	user = root
	password = admin
	
Troubleshooting points

1) for mounting files use ${pwd} inside default nginx
2) the VOLUME inside Dockerfile doesnt allow to mount the host directory
   whatever you mount is for the container directory 
	ex: VOLUME /usr/jmeter/results
	creates a new empty folder everytime you run 
	
	by default it goes to /var/lib/docker/volumes in docker host 
	so it can be overridden in runtime by the following command 
	
	docker run -v /c/users/karigar/Desktop/:/user/jmeter/results