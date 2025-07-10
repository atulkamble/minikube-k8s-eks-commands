**command list for Minikube, Kubernetes (kubectl), and EKS (eksctl & AWS CLI)**. You can bookmark this as a cheat sheet too.

---

## 📄 Minikube Commands

| Action                     | Command                               |
| :------------------------- | :------------------------------------ |
| Start Minikube             | `minikube start`                      |
| Start with specific driver | `minikube start --driver=docker`      |
| Stop Minikube              | `minikube stop`                       |
| Delete Minikube cluster    | `minikube delete`                     |
| Check Minikube status      | `minikube status`                     |
| Get Minikube IP            | `minikube ip`                         |
| Dashboard UI               | `minikube dashboard`                  |
| SSH into Minikube VM       | `minikube ssh`                        |
| Set Kubernetes context     | `kubectl config use-context minikube` |

---

## 📄 Kubernetes (kubectl) Commands

### Cluster & Nodes

| Action                 | Command                  |
| :--------------------- | :----------------------- |
| Check cluster info     | `kubectl cluster-info`   |
| List nodes             | `kubectl get nodes`      |
| Get detailed node info | `kubectl describe nodes` |

### Pods

| Action                 | Command                                    |
| :--------------------- | :----------------------------------------- |
| List all pods          | `kubectl get pods`                         |
| List pods in namespace | `kubectl get pods -n <namespace>`          |
| Pod details            | `kubectl describe pod <pod-name>`          |
| Pod logs               | `kubectl logs <pod-name>`                  |
| Exec into pod          | `kubectl exec -it <pod-name> -- /bin/bash` |

### Deployments

| Action            | Command                                        |
| :---------------- | :--------------------------------------------- |
| List deployments  | `kubectl get deployments`                      |
| Create from YAML  | `kubectl apply -f <file.yaml>`                 |
| Update deployment | `kubectl apply -f <updated-file.yaml>`         |
| Delete deployment | `kubectl delete deployment <name>`             |
| Scale deployment  | `kubectl scale deployment <name> --replicas=3` |

### Services

| Action            | Command                                                                             |
| :---------------- | :---------------------------------------------------------------------------------- |
| List services     | `kubectl get services`                                                              |
| Expose deployment | `kubectl expose deployment <name> --type=LoadBalancer --port=80 --target-port=8080` |
| Service details   | `kubectl describe service <name>`                                                   |

### Config & Namespaces

| Action               | Command                             |
| :------------------- | :---------------------------------- |
| List namespaces      | `kubectl get namespaces`            |
| Create namespace     | `kubectl create namespace <name>`   |
| Delete namespace     | `kubectl delete namespace <name>`   |
| View config contexts | `kubectl config get-contexts`       |
| Switch context       | `kubectl config use-context <name>` |

---

## 📄 Amazon EKS (eksctl & AWS CLI)

### eksctl Commands

| Action           | Command                                                                                         |
| :--------------- | :---------------------------------------------------------------------------------------------- |
| Create cluster   | `eksctl create cluster --name <cluster-name> --region <region> --nodes 2 --node-type t2.medium` |
| Delete cluster   | `eksctl delete cluster --name <cluster-name>`                                                   |
| Get EKS nodes    | `kubectl get nodes`                                                                             |
| Create nodegroup | `eksctl create nodegroup --cluster <name> --region <region>`                                    |
| Delete nodegroup | `eksctl delete nodegroup --cluster <name> --name <nodegroup-name>`                              |

### AWS CLI EKS Commands

| Action            | Command                                                             |
| :---------------- | :------------------------------------------------------------------ |
| List EKS clusters | `aws eks list-clusters --region <region>`                           |
| Describe cluster  | `aws eks describe-cluster --name <cluster-name> --region <region>`  |
| Update kubeconfig | `aws eks update-kubeconfig --name <cluster-name> --region <region>` |

---

## 📌 Bonus Useful Commands

| Purpose                           | Command                          |
| :-------------------------------- | :------------------------------- |
| List all resources in a namespace | `kubectl get all -n <namespace>` |
| Delete all resources from a file  | `kubectl delete -f <file.yaml>`  |
| Get Kubernetes version            | `kubectl version --short`        |
| Get Minikube Kubernetes version   | `minikube kubectl -- version`    |

---

## 📄 Example YAML Deployment (Quick Ref)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

---

