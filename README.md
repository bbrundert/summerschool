# summerschool-demo
Building a simple nginx container image, pushing it to Docker Hub and running it on Kubernetes
Demo prepared for VMware Germany Summer School event 2019.

Special thanks to Alexander Dess (@AlexanderDess) for https://github.com/appdess/vmc-nginx-demo!


Commands:
1) Build container image:
```
cd Docker
docker build .
docker images
```

2) Tag image locally:
```
docker tag <ID> <registry-FQDN>/<repository>/<image-name>:<tag> 
# docker tag 8c9fc5afa0e7 harbor.cpod-bbrundert01.az-lab.shwrfr.com/summerschool/modernapps-nginx:v2
```

3) Push image to registry:
```
docker push <registry-FQDN>/<repository>/<image-name>:<tag>
#docker push harbor.cpod-bbrundert01.az-lab.shwrfr.com/summerschool/modernapps-nginx:v2
```

4) Deploy to Kubernetes
```
cd ../Deploy-nginx-yaml
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml
```
