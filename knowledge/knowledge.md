# ACM knowledge

- detach cluster means delete the managedcluster resource, do not delete clusterclaim.hive
- stop/hibernating/resume/start cluster should follow doc(https://github.com/openshift/hive/blob/master/docs/hibernating-clusters.md) 
    example: 
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Hibernating' -n mycluster
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Running' -n mycluster
- claim a cluster means create a clusterclaim.hive, you can get example in current env in current namespace.
- Add label `do-not-hibernate=true` to a claim-name will make the cluster do not hibernate automatically.
- Add label `do-not-delete=true` to a claim will make the cluster do not delete automatically.


