# ACM knowledge
- Detach cluster means delete the managedcluster resource, do not delete clusterclaim.hive
- stop/hibernating/resume/start cluster should follow doc(https://github.com/openshift/hive/blob/master/docs/hibernating-clusters.md) 
    example: 
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Hibernating' -n mycluster
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Running' -n mycluster
- Claim a cluster means create a clusterclaim.hive, you can get example in current env in current namespace.


# Collective ACM enviroment
- Collective cluster api server: https://api.collective.aws.red-chesterfield.com:6443
- Add label `do-not-hibernate=true` to a claim-name will make the cluster do not hibernate automatically, but can still hibernate the cluster by patching the clusterdeployment mannually.
- Add label `do-not-delete=true` to a claim will make the cluster do not delete automatically, but can still delete the cluster manually.


# WorkFlow
## Install Globalhub
- switch to use globalhub cluster
- switch to globalhub code directory
- run `cd operator` and  `make deploy` to deploy globalhub operator
- apply the globalhub cr: `oc apply -f config/samples/operator_v1alpha4_multiclusterglobalhub.yaml`
