# kubernetes-course
Curso de kubernetes:

Referencias:
https://github.com/roxsross/k8sonfire

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