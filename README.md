# kubernetes-course
Curso de kubernetes:

Referencias:
https://github.com/roxsross/k8sonfire
https://killercoda.com

### Problemas encontrados durante este curso
Si tienes problemas para instalar lens in linux:

Borra el archivo nosnap.pref:
    
    sudo rm /etc/apt/preferences.d/nosnap.pref

Actualiza apt:

    sudo apt update

Instala snapd:

    sudo apt install snapd

Baja el archivo .snap de la pagina oficial

Instala lens:

    sudo snap install Lens-{version}.amd64.snap --dangerous --classic
Ejemplo:
    sudo snap install Lens-2022.10.181357-latest.amd64.snap --dangerous --classic

Iniciar lens:
    lens

Referencia: 
https://unix.stackexchange.com/questions/593366/how-to-enable-snaps-support-on-linux-mint-20


### Challenge 1
Los comandos utilizados en este reto fueron los siguientes:
    
    minikube start

    minikube status

    kubectl get nodes -o wide

    minikube stop

### Challenge 2
Los comandos utilizados en este reto fueron los siguientes:
    
    minikube start

    kubectl create -f pod.yaml

    kubectl get pods

    kubectl get pod -o wide

    kubectl exec -it pod-k8s-test-web -- /bin/sh

    kubectl port-forward pod-k8s-test-web 8888:80

    kubectl logs pod-k8s-test-web

    kubectl delete pod pod-k8s-test-web

    minikube stop

### Challenge 3
Los comandos utilizados en este reto fueron los siguientes:
    
    minikube start

    kubectl create -f pod-multicontenedor.yaml

    kubectl get pods

    kubectl exec pod-multicontenedor -c contenedor1 -- /bin/cat /usr/share/nginx/html/index.html

    kubectl exec pod-multicontenedor -c contenedor2 -- /bin/cat /html/index.html

    kubectl port-forward pod-multicontenedor 8081:80

    minikube stop

### Challenge 4
Los comandos utilizados en este reto fueron los siguientes:

    minikube start

    kubectl apply -f rs.yaml

    kubectl get rs,pods

    kubectl describe rs replicaset-k8s-test-web

    kubectl delete pod [nombre_pod]

    kubectl get pods

    kubectl scale rs replicaset-k8s-test-web --replicas=4

    kubectl get pods

    kubectl delete rs replicaset-k8s-test-web

    minikube stop

### Challenge 5
Los comandos utilizados en este reto fueron los siguientes:

    minikube start

    kubectl apply -f deploy.yaml

    kubectl get deploy,rs,pods

    kubectl describe deployment/deployment-k8s-test-web

    kubectl port-forward deployment/deployment-k8s-test-web 8080:80

    kubectl logs deployment/deployment-k8s-test-web
    
    kubectl get all

    kubectl scale deployment deployment-k8s-test-web --replicas=4

    kubectl delete deployment deployment-k8s-test-web

    kubectl get pods

    minikube stop

### Challenge 6
Los comandos utilizados en este reto fueron los siguientes:

    minikube start

    kubectl apply -f deploy.yaml

    kubectl annotate deployment/deployment-k8s-test-web kubernetes.io/change-cause="Despliegue versión 1"

    kubectl get all

    kubectl port-forward deployment/deployment-k8s-test-web 8080:80

    kubectl apply -f deploy.yaml
    
    kubectl annotate deployment/deployment-k8s-test-web kubernetes.io/change-cause="Despliegue versión 2"

    kubectl port-forward deployment/deployment-k8s-test-web 8080:80
    
    kubectl rollout history deployment/deployment-k8s-test-web
    
    kubectl apply -f deploy.yaml
    
    kubectl annotate deployment/deployment-k8s-test-web kubernetes.io/change-cause="Despliegue versión 3"

    kubectl port-forward deployment/deployment-k8s-test-web 8080:80

    kubectl rollout history deployment rollout history deployment-k8s-test-web
    
    kubectl get all

    kubectl rollout history deployment/deployment-k8s-test-web

    kubectl delete deployment/deployment-k8s-test-web

    kubectl get pods

    minikube stop

### Comandos en general
ReplicaSet:
    
    kubectl get rs
    
    kubectl get rs,pods
    
    kubectl describe rs/frontend
    
    kubectl apply -f [file]

    kubectl config view --minify --raw