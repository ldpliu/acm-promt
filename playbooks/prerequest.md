You should follow this prerequest when you do any action.

# Prerequest

## Common
- must get approve when do any create/update/delete/patch/apply actions which may need change cluster resource.

## My
- should use "oc project acm-hub-of-hubs" swith to namespace "acm-hub-of-hubs"
- all my cluster related clusterclaim.hive name has prefix “liudp-”
- store all my clusters kubeconfig file to ~/.kube/config-<Claim Name>
- my globalhub kubeconfig: ~/.kube/config-liudp-gh1
- globalhub code directory: ~/go/src/github.com/stolostron/multicluster-global-hub
