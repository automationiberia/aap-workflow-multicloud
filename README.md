# aap-workflow-multicloud

## Packages required

```
$  python3 -m pip install ansible-navigator --user
$  python3 -m pip install ansible-builder --user
```
## Populate and encrypt your credentials and custom data

```
$ vim group_vars/all/configure_connection_credentials.yaml
$ ansible-vault encrypt group_vars/all/configure_connection_credentials.yaml
```
## Create AAP objects

```
$ ansible-navigator run deploy.yaml -i inventory -m stdout --eei quay.io/automationiberia/ee-casc:latest --vault-password-file .vault_password
```
