# Globalhub Env:
- idf <<globalhub kubeconfig>>: ~/.kube/config-gh
- <<globalhub code dir>>: ~/go/src/github.com/stolostron/multicluster-global-hub

# Prerequest
- switch to use globalhub cluster by `export KUBECONFIG=<globalhub kubeconfig>`
- run `oc project multicluster-global-hub` to swith to globalhub namespace

# WorkFlow
## Install Globalhub
- switch to globalhub code directorycd
- run `cd <globalhub code dir>/operator` and  `make deploy` to deploy globalhub operator
- apply the globalhub cr: `oc apply -f config/samples/operator_v1alpha4_multiclusterglobalhub.yaml`

## Install Globalhub with my image
- switch to globalhub code directory
- run `make build-operator-image && docker tag quay.io/stolostron/multicluster-global-hub-operator:latest quay.io/ldpliu/multicluster-global-hub-operator:latest && docker push quay.io/ldpliu/multicluster-global-hub-operator:latest`
- run `cd operator` and  `make deploy` to deploy globalhub operator
- update the deployment `multicluster-global-hub-operator` container image to `quay.io/ldpliu/multicluster-global-hub-operator:latest`
- apply the globalhub cr: `oc apply -f config/samples/operator_v1alpha4_multiclusterglobalhub.yaml`

## Reinstall Globalhub with my image
- Uninstall Globalhub 
- Install Globalhub with my image

## UnInstall Globalhub
- switch to globalhub code directory
- delete mgh by `oc delete mgh --all`
- run `cd operator` and  `make undeploy` to deploy globalhub operator

## Reinstall Globalhub
- Uninstall Globalhub 
- Install Globalhub
