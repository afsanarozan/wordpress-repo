## first Installation using Docker
 
You can clone this repo to your local computer

```console
$ git repo clone afsanarozan/wordpress-repo
```

requirement

1. install docker 
2. Installed Docker composer 
 

### Reference https://docs.docker.com/compose/install/ 

## Install Wordpress 

```console
$ docker-compose up -d
```
```console
$ docker ps 
```
```console
bitnami/wordpress:5    "/opt/bitnami/script…"   19 hours ago   Up 42 minutes   0.0.0.0:8081->8080/tcp, :::8081->8080/tcp, 0.0.0.0:443->8443/tcp, :::443->8443 
bitnami/mariadb:10.3   "/opt/bitnami/script…"   19 hours ago   Up 42 minutes   3306/tcp                                                                            
```

to make sure the containers has been running

3. So you can akses the application (IP):8081

4. you_can akses WP_admin by path (ip):8081/login  
   
   username nopal
   password hahaha321
   
   if can't login you can using default env 

   username user
   password bitnami

Instalation Using Helm Kubernetes 

1. Kubernetes cluster, your can using minikube 
2. Install Helm Chart in your device 
3. add repo helm using command
   helm repo add bitnami https://charts.bitnami.com/bitnami

4. helm repo update 
5. you can take the values yaml with command
   helm show values bitnami/wordpress
6. or using my values.yaml in my repo
   there is HPA for scale up pod if there is user growing
   and i setup domain ingress demo.wordpress.local (optional) you can change in values.yaml
7. so install app using command
   helm install (nama application) bitnami/wordpress -f values.yaml -n (nama_namespace(optional)) 

8. check application 
   kubetl get all -n (nama_namespace(optional))

9. you can akses with ingress in domain demo.wordpress.local if you are using minikube in local
8. but if on cloud you can install inginx-ingresscontroller first and set up annotation ingressClass in ingress your application 
10. if you will login youcan demo.wordpress.local/login so you can login by username = nopal, password = hahaha321 

