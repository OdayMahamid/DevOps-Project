# devOps-project


## Solution steps
* Create html file `index.html` that display my name and my DOB as plain text 
* Dockerfile:
```
FROM nginx:latest
# Copy html file from the current dir to the nginx image
COPY ./index.html /usr/share/nginx/html/index.html
```

* Create Jenkinsfile that incalude script to build and push the image in to Dockerhub, we run it in the jenkins


* Create a deployment yml named `deployment yml` with service:
    * import image from dockerhub that I have created 
    * Expose the deploy using type = ClusterIP
    * port 80

* Create Ingress yml neamed `Ingress.yml` that manages external access to the services in a cluster.
    * Path `/` 
    * Port 80 





## Run the project:

    $ git clone https://github.com/OdayMahamid/devOps-project.git
    $ cd devOps-project
    $ kubectl apply -f deployment.yml
    $ kubectl apply -f Ingress.yml

You can access the application here: http://localhost/

![Screenshot from 2021-12-05 23-35-52](https://user-images.githubusercontent.com/58177069/144765033-8f3c958a-1c9c-4444-870a-d031e05fe1c1.png)

