# Hive testing

## Install hive operator

Apply kustomization

```bash
export aws_access_key_id=`<your_access_key_id>`
export aws_secret_access_key=`<your_access_key_secret>`

# save openshift pull secret as hive-operator/dockerconfig.json

# IF you want to use ssh keys
export ssh_privatekey="$(cat ~/.ssh/id_rsa)" # Or whatever private key to use
export ssh_publickey="$(cat ~/.ssh/id_rsa.pub)"

kustomize build hive-operator | kubectl apply -f -
```

## Configure Hive operator

Modify `example-config/hiveconfig.yaml` and apply

## Try sample deployment

see [example-deployment](example-deployment)

## Try clusterpool

see [example-clusterpool](example-clusterpool)

## Access clusters

Get the get-kubeconfig script:

```bash
wget https://raw.githubusercontent.com/openshift/hive/master/hack/get-kubeconfig.sh

./get-kubeconfig.sh ${CLUSTER_NAME} > ${CLUSTER_NAME}.kubeconfig
export KUBECONFIG=${CLUSTER_NAME}.kubeconfig
oc get nodes
```

## What's next

https://github.com/openshift/certman-operator
