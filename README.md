
## This is a basic side car example using NGINX
I originally found this [article](https://www.magalix.com/blog/implemeting-a-reverse-proxy-server-in-kubernetes-using-the-sidecar-pattern) with several typos explaining the basic concept of a Nginx side car. To summarize you add a proxy like Nginx that is a container in the same pod as your application. You can modify the default.conf in this example repo to change how nginx routes the traffic. You can access each othe ther containers using localhost:port and direct based on a url.

### Project Setup
* Clone this repo `git clone ` and open the folder in your favorite terminal
* Next run `kubectl apply -f deployment.yml` to launch the deployment.
* Open [localhost:32001](http://localhost:32001/) in your browswer and you should be greated with a message from the backend api
* To remove the project `kubectl delete -f deployment.yml`

### Building the images:
* Nginx
  * You can build the nginx image with `docker build -t <YOUR DOCKER HUB USERNAME>/flask-nginx-sidecar -f Dockerfiles/nginx/Dockerfile .`
  * If you want to use this image in kubernetes push it to your docker hub account `docker push <YOUR DOCKER HUB USERNAME>/flask-nginx-sidecar` 
* Flask
  * You can build the flask image with `docker build -t <YOUR DOCKER HUB USERNAME>/flasksidecar -f Dockerfiles/nginx/Dockerfile .`
  * If you want to use this image in kubernetes push it to your docker hub account `docker push <YOUR DOCKER HUB USERNAME>/flask-nginx-sidecar` 


