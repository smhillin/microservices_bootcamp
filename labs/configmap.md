
# Config Map Example

## Step One: Create the ConfigMap

#### Download Yaml File
`wget http://pwittrock.github.io/docs/user-guide/configmap/configmap.yaml`


#### You can use kubectl to see information about the ConfigMap:



`kubectl get configmap`


`kubectl describe configMap test-configmap`


#### View the values of the keys with kubectl get:


`kubectl get configmaps test-configmap -o yaml`


## Step Two: Create a pod that consumes a configMap in environment variables

#### Use the env-pod.yaml file to create a Pod that consumes the ConfigMap in environment variables.

 `kubectl create -f docs/user-guide/configmap/env-pod.yaml`

#### This pod runs the env command to display the environment of the container:

`kubectl logs config-env-test-pod | grep KUBE_CONFIG`


## Step Three: Create a pod that sets the command line using ConfigMap

#### Use the command-pod.yaml file to create a Pod with a container whose command is injected with the keys of a ConfigMap

`kubectl create -f docs/user-guide/configmap/command-pod.yaml`

#### This pod runs an echo command to display the keys:

`kubectl logs config-cmd-test-pod`

## Step Four: Create a pod that consumes a configMap in a volume

#### Pods can also consume ConfigMaps in volumes. Use the volume-pod.yaml file to create a Pod that consume the ConfigMap in a volume.


`kubectl create -f docs/user-guide/configmap/volume-pod.yaml`


#### This pod runs a cat command to print the value of one of the keys in the volume:

`kubectl logs config-volume-test-pod`
