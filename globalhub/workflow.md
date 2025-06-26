# Globalhub Env:
- my globalhub kubeconfig: ~/.kube/config-liudp-gh1
- globalhub code directory: ~/go/src/github.com/stolostron/multicluster-global-hub

# Prerequest
- switch to use globalhub cluster by `export KUBECONFIG=<Globalhub kubeconfig>`
- run `oc project multicluster-global-hub` to swith to globalhub namespace

# WorkFlow
## Install Globalhub
- switch to globalhub code directory
- run `cd operator` and  `make deploy` to deploy globalhub operator
- apply the globalhub cr: `oc apply -f config/samples/operator_v1alpha4_multiclusterglobalhub.yaml`

## UnInstall Globalhub
- switch to globalhub code directory
- delete mgh by `oc delete mgh --all`
- run `cd operator` and  `make undeploy` to deploy globalhub operator

## Reinstall Globalhub
- Uninstall Globalhub 
- Install Globalhub
