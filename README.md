# Why
Provide a tools to use AI to make ACM more easy to use, and make the AI tool behavior more accurate and controlled.


# acm-promt

# use cases

## clusters 
1. claim a cluster from cluster pool
2. create a clusterpool based on latest ocp 4.19 images
3. get user passwd/ consol link of a cluster.
4. import cluster <xxx> to xxx
5. create a acm hub
6. hibernate all my clusters
7. resume all my clusters
8. create a cronjob to hierbernate all clusters in ns
9. migrate the clusters to hub2

## policies



# process -> suggestion


# other notes
## prerequest
1. use kubeconfig? if not use ~/.kube/config
2. my namespace
3. my cluster name format

- all the kubeconfig file in ~/.kube
- if the kubeconfig is config-colle, should use `oc project acm-hub-of-hubs` swith to namespace `acm-hub-of-hubs`
- if the kubeconfig is config-colle, all my cluster(clusterclaim.hive) name has prefix `liudp-`
