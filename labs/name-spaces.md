# Kubernetes Namespaces

#### Get default namespaces

`kubectl get ns`

#### Create a ‘test’ namespace

`kubectl create -f https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/ns/ns.yaml`

#### Recheck namespaces and observe

`kubectl get ns`

#### Now create a pod in this new namespace

`kubectl create --namespace=test -f https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/ns/pod.yaml`

#### Check pods in this new namespace

`kubectl get pods --namespace=test`
