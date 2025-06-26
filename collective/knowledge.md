# ACM knowledge
- Detach cluster means delete the managedcluster resource, do not delete clusterclaim.hive
- stop/hibernating/resume/start cluster should follow doc(https://github.com/openshift/hive/blob/master/docs/hibernating-clusters.md) 
    example: 
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Hibernating' -n mycluster
    $ oc patch clusterdeployment mycluster --type='merge' -p $'spec:\n powerState: Running' -n mycluster
- Claim a cluster means create a clusterclaim.hive, you can get example in current env in current namespace.
