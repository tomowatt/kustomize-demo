# kustomize-demo

Demonstration of using Kustomize to deploy to multiple namespaces/environments with different Images and Configurations. Which can be combined with CI/CD Tools triggered by Git Tags for automated deployments.

Using the upstream Kustomize - requiring to 'build | apply' - over version included with 'kubectl' due to it lagging with current version causing issues and not fully compatible with current Kustomize documentation.


Install Kustomize:

<https://kubectl.docs.kubernetes.io/installation/kustomize/>

Create namespace(s):

```sh
kubectl create namespace [staging|uat|live]
```

Apply manifests:

```sh
kustomize build [staging|uat|live] | kubectl apply -f - 
```

Clean up:

```sh
kustomize build [staging|uat|live] | kubectl delete -f - 
```
