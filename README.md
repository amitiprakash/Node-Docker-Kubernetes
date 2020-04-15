# Node-Docker-Kubernetes
Learning node, docker and kubernetes for cloud native

1. npm install express-generator -g
		build a template application from which we can do development.
2. Create a docker file
	https://www.cloudnativejs.io/
	docker in git
	copy the DockerFile and .dockerignore file
	docker build -t nodeserver -f Dockerfile .
	docker images ==> to find all the running images
	docker run -i -p 3000:3000 -t nodeserver ==> -i interactively
	
3.	Dockerfile-Tools use run-dev and run-debug to run the application in development in debug mode

	docker build -t nodeserver-tools -f Dockerfile-tools .
	docker run -i -v "$PWD"/package.json:/tmp/package.json -v "$PWD"/node_modules_linux:/tmp/node_modules -w /tmp -t node:10 npm install
	dev mode
	docker run -i -p 3000:3000 -v "$PWD"/:/app -v "$PWD"/node_modules_linux:/app/node_modules -t my-nodejs-application-tools /bin/run-dev
	
	debug mode
	docker run -i --expose 9229 -p 9229:9229 -p 3000:3000 -v "$PWD"/:/app -v "$PWD"/node_modules_linux:/app/node_modules -t my-nodejs-application-tools /bin/run-debug