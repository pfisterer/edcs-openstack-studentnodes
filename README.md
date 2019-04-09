# Ansible script to generate virtual machines in OpenStack for students

Creates a number of virtual machines with

Provides remote access to
- SSH (native or web interface)
- a graphical desktop (VNC via web interface or RDP via client)

## Usage

1. Set the required environment variables
2. Run `ansible-playbook deploy.yaml`
3. See `generated-server-list.txt` for the IP adresses of the created machines
4. Open <https://IP-adress> and ignore the security warning

## Environment variables

| Name             | Optional | Description                       |
| ---------------- | -------- | --------------------------------- |
| NODE_COUNT       | x        | Number of nodes to creates        |
| NODE_PASSWORD    |          | Password to set for user `ubuntu` |
| NODE_NAME        | x        | Prefix for hostnames              |
| IMAGE            |          | Name of the OS image to use       |
| NODE_FLAVOR      |          | Name of the machine flavor to use |
| NODE_SEC_GROUP   |          | Security group to use             |
| KEY              |          | Name of the SSH key to use        |
| EXT_NET          |          | Name of the external network      |
| FLOATING_IP_POOL |          | Name of the floating IP pool      |
| DNS_SERVER_1     | x        | DNS server #1                     |
| DNS_SERVER_1     | x        | DNS server #2                     |

For default values, see [group_vars/all.yaml](group_vars/all.yaml)

Standard OpenStack environment variables, such as:
- `OS_PROJECT_NAME`
- `OS_DOMAIN_NAME`
- `OS_AUTH_URL`
- `OS_PASSWORD`
- `OS_USERNAME`
