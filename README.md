# kubernetes-course
Curso de kubernetes:

Referencias:
https://github.com/roxsross/k8sonfire

### Challenge 1
Los comandos utilizados en este reto fueron los siguientes:
    minikube start

    minikube status

    kubectl get nodes -o wide

### Challenge 2
Los comandos utilizados en este reto fueron los siguientes:
    kubectl create -f pod.yaml

    kubectl get pods

    kubectl get pod -o wide

    kubectl exec -it pod-k8s-test-web -- /bin/sh

    kubectl port-forward pod-k8s-test-web 8888:80

    kubectl logs pod-k8s-test-web

    kubectl delete pod pod-k8s-test-web