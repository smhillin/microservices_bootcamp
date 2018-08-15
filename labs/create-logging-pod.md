# Create a Logging Pod

`kubectl`

#### Grab the last few lines of logs

`kubectl logs --tail=5 logme -c gen`

#### Grab a stream of the logs

`kubectl logs -f --since=10s logme -c gen`

#### Clean up

`kubectl delete -f https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/logging/pod.yaml`

#### Now launch a container that performs an action and then exits. Give it a minute or so to close out

`kubectl create -f https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/logging/oneshotpod.yaml`

#### Now output the logs of this container

`kubectl logs -p oneshot -c gen`

#### Clean up

`kubectl delete -f https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/logging/oneshotpod.yaml`

http://kubernetesbyexample.com/logging/
