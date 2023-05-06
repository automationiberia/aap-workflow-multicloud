# aap-workflow-multicloud

## Packages required

```
$  python3 -m pip install ansible-navigator --user
$  python3 -m pip install ansible-builder --user
```
## Populate and encrypt your credentials and custom data

```
$ vim .vault_password
$ vim group_vars/controller/controller_credentials.yaml group_vars/eks/configure_connection_credentials.yaml group_vars/ocp/configure_connection_credentials.yaml group_vars/controller/configure_connection_credentials.yaml
$ ansible-vault encrypt group_vars/controller/controller_credentials.yaml group_vars/eks/configure_connection_credentials.yaml group_vars/ocp/configure_connection_credentials.yaml group_vars/controller/configure_connection_credentials.yaml
```
## Create AAP objects

```
$ ansible-navigator run deploy.yaml -i inventory -m stdout --eei quay.io/automationiberia/aap/ee-casc:latest --vault-password-file .vault_password
$ ansible-navigator run create_k8s_objects.yaml -i inventory -m stdout --eei quay.io/automationiberia/ee-ocp-aap-iac-casc:latest --vault-password-file .vault_password
$ ansible-navigator run get_k8s_cluster_info.yaml -i inventory -m stdout --eei quay.io/automationiberia/ee-ocp-aap-iac-casc:latest --vault-password-file .vault_password
```
