# Mcrouter Ansible Operator

## Quickstart

1. Start [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/) (e.g. `minikube start`)

    We will be using the `default` namespace, and the `default` account


1. Deploy the Mcrouter Ansible Operator

    * Create the Mcrouter Ansible Operator RBAC and Service Account files
        ```bash
        $ kubectl create -f deploy/service_account.yaml
        $ kubectl create -f deploy/role.yaml
        $ kubectl create -f deploy/role_binding.yaml
        ```

    * Create the Mcrouter Ansible Operator Custom Resource Definitions (CRD)
        ```bash
        kubectl create -f deploy/crds/cache_v1alpha2_mcrouter_crd.yaml
        ```
    * Deploy the Mcrouter Ansible Operator
        ```bash
        kubectl create -f deploy/operator.yaml
        ```

1. Create the Mcrouter Ansible Operator Custom Resource (CR)

    ```bash
    kubectl create -f deploy/crds/cache_v1alpha2_mcrouter_cr.yaml
    ```

## Uninstall

To uninstall the Deployment and the Mcrouter Ansible Operator, run the following commands

1. Uninstall
    ```bash
    kubectl delete -f deploy/crds/cache_v1alpha2_mcrouter_cr.yaml
    ```
1. Uninstall Mcrouter Ansible Operator
    ```bash
    kubectl delete -f deploy/operator.yaml
    ```

Verify that the all pods created with the deployment are being `terminated` and are deleted
