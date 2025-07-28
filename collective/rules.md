You should follow this prerequest when you do any action.

# Prerequest
- must get approve when do any create/update/delete/patch/apply actions which may need change cluster resource.
- switch to use collective cluster by `export KUBECONFIG=~/.kube/config-collective`
- should login to collective cluster by `oc login https://api.collective.aws.red-chesterfield.com:6443 --web` when it's unaccessible
- should use "oc project acm-hub-of-hubs" swith to namespace "acm-hub-of-hubs"
- all my cluster related clusterclaim.hive name has prefix “liudp-”


## Collective ACM enviroment
- Collective cluster api server: https://api.collective.aws.red-chesterfield.com:6443
- Add label `do-not-hibernate=true` to a claim-name will make the cluster do not hibernate automatically, but can still hibernate the cluster by patching the clusterdeployment mannually.
- Add label `do-not-delete=true` to a claim will make the cluster do not delete automatically, but can still delete the cluster manually.

# ACM knowledge
- Detach cluster means delete the managedcluster resource, do not delete clusterclaim.hive
- stop/hibernating/resume/start cluster should follow doc(https://github.com/openshift/hive/blob/master/docs/hibernating-clusters.md) 
    example: 
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Hibernating' -n mycluster
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Running' -n mycluster
- Claim a cluster means create a clusterclaim.hive, you can get example in current env in current namespace.
