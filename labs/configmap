

#### Download Yaml File
`wget http://pwittrock.github.io/docs/user-guide/configmap/configmap.yaml`


#### You can use kubectl to see information about the ConfigMap:


`
$ kubectl get configmap
NAME                   DATA      AGE
test-configmap         2         6s

$ kubectl describe configMap test-configmap
Name:          test-configmap
Labels:        <none>
Annotations:   <none>

Data
====
data-1: 7 bytes
data-2: 7 bytes`
`

#### View the values of the keys with kubectl get:


`
$ kubectl get configmaps test-configmap -o yaml
apiVersion: v1
data:
  data-1: value-1
  data-2: value-2
kind: ConfigMap
metadata:
  creationTimestamp: 2016-02-18T20:28:50Z
  name: test-configmap
  namespace: default
  resourceVersion: "1090"
  selfLink: /api/v1/namespaces/default/configmaps/test-configmap
  uid: 384bd365-d67e-11e5-8cd0-68f728db1985
 `

## Step Two: Create a pod that consumes a configMap in environment variables

#### Use the env-pod.yaml file to create a Pod that consumes the ConfigMap in environment variables.

 `$ kubectl create -f docs/user-guide/configmap/env-pod.yaml`

#### This pod runs the env command to display the environment of the container:

'$ kubectl logs config-env-test-pod | grep KUBE_CONFIG
KUBE_CONFIG_1=value-1
KUBE_CONFIG_2=value-2
'

## Step Three: Create a pod that sets the command line using ConfigMap

#### Use the command-pod.yaml file to create a Pod with a container whose command is injected with the keys of a ConfigMap

`$ kubectl create -f docs/user-guide/configmap/command-pod.yaml`

#### This pod runs an echo command to display the keys:

'
$ kubectl logs config-cmd-test-pod
value-1 value-2
'

## Step Four: Create a pod that consumes a configMap in a volume

#### Pods can also consume ConfigMaps in volumes. Use the volume-pod.yaml file to create a Pod that consume the ConfigMap in a volume.

'
$ kubectl create -f docs/user-guide/configmap/volume-pod.yaml'


#### This pod runs a cat command to print the value of one of the keys in the volume:

'
$ kubectl logs config-volume-test-pod
value-1
'
