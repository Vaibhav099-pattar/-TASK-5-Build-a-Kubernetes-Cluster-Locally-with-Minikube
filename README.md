Project Name: Build a Kubernetes Cluster Locally with Minikube
Before you begin, ensure you have the following installed on your system:
- [Docker] Already installed for previous task
- [Minikube] https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download
- [kubectl ] https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
**Kubernetes with Minikube –Deployment Setup**
Start Your Minikube Cluster:minikube start
Create Deployment Configuration (deployment.yaml)
Apply the Deployment:kubectl apply -f deployment.yaml
Create Service Configuration (service.yaml)
Apply the Service:kubectl apply -f service.yaml
minikube service nginx-service --url:http://192.168.49.2:30007
Verify with kubectl:kubectl get pods
vaibhav@localhost ~]$ kubectl get pods
NAME                              READY   STATUS    RESTARTS   AGE
nginx-deployment-96b9d695-6dzj5   1/1     Running   0          2m18s
nginx-deployment-96b9d695-bj5tv   1/1     Running   0          2m18s
Scale the Deployment:kubectl scale deployment nginx-deployment --replicas=5
kubectl get pods:
[vaibhav@localhost ~]$ kubectl get pods
NAME                              READY   STATUS              RESTARTS   AGE
nginx-deployment-96b9d695-6dzj5   1/1     Running             0          5m56s
nginx-deployment-96b9d695-bj5tv   1/1     Running             0          5m56s
nginx-deployment-96b9d695-ch659   1/1     Running             0          12s
nginx-deployment-96b9d695-jzbwb   1/1     Running             0          12s
nginx-deployment-96b9d695-tnv7t   0/1     ContainerCreating   0          12s
