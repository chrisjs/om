&larr; [back to `configure-bosh`](README.md)

# Azure-specific inputs for the `configure-bosh` command

#### --iaas-configuration

##### Minimal example
```json
{
  "subscription_id": "some-subscription-id",
  "tenant_id": "some-tenant-id",
  "client_id": "some-client-id",
  "client_secret": "some-client-id",
  "resource_group_name": "some-resource-group-name",
  "bosh_storage_account_name": "some-bosh-storage-account-name",
  "deployments_storage_account_name": "some-deployments-storage-account-name",
  "default_security_group": "some-default-security-group",
  "ssh_public_key": "some-ssh-public-key",
  "ssh_private_key": "some-ssh-private-key"
}
```

#### --director-configuration

##### Minimal example
```json
{
  "ntp_servers_string": "us.pool.ntp.org"
}
```

#### --security-configuration
No additional security configuration is strictly required.

##### Minimal example
```json
{
  "trusted_certificates": "some-trusted-certificates",
  "vm_password_type": "generate"
}
```

#### --az-configuration
Azure does not configure or manage AZs and so this configuration is not required.

#### --networks-configuration

##### Minimal example
```json
{
  "networks": [
    {
      "name": "opsman-network",
      "iaas_identifier": "some-network/some-opsman-subnet",
      "subnets": [
        {
          "cidr": "10.0.8.0/26",
          "reserved_ip_ranges": "10.0.8.0-10.0.8.4",
          "dns": "8.8.8.8",
          "gateway": "10.0.8.1"
        }
      ]
    },
    {
      "name": "ert-network",
      "iaas_identifier": "some-network/some-ert-subnet",
      "subnets": [
        {
          "cidr": "10.0.0.0/22",
          "reserved_ip_ranges": "10.0.0.0-10.0.0.4",
          "dns": "8.8.8.8",
          "gateway": "10.0.0.1"
        }
      ]
    },
    {
      "name": "services-network",
      "iaas_identifier": "some-network/some-services-subnet",
      "subnets": [
        {
          "cidr": "10.0.4.0/22",
          "reserved_ip_ranges": "10.0.4.0-10.0.4.4",
          "dns": "8.8.8.8",
          "gateway": "10.0.4.1"
        }
      ]
    }
  ]
}
```

#### --network-assignment

##### Minimal example
```json
{
  "network": "opsman-network"
}
```
