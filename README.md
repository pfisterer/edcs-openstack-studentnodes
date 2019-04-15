# Ansible Playbook for Generating Virtual Machines in OpenStack for Students

Creates a number of virtual machines with

Provides remote access to
- SSH (native or web interface)
- a graphical desktop (VNC via web interface or RDP via client)

Original Github repo: <https://github.com/pfisterer/edsc-openstack-studentnodes>

## Usage

1. Set the required environment variables
2. Run `ansible-playbook deploy.yaml`
3. See `generated-server-list.txt` for the IP adresses of the created machines
4. Open <https://IP-adress> and ignore the security warning

## Environment Variables

| Name             | Required | Description                         |
| ---------------- | -------- | ----------------------------------- |
| NODE_COUNT       |          | Number of nodes to creates          |
| NODE_PASSWORD    | x        | Password to set for user `ubuntu`   |
| NODE_NAME        |          | Prefix for hostnames                |
| IMAGE            | x        | Name of the OS image to use         |
| NODE_FLAVOR      | x        | Name of the machine flavor to use   |
| NODE_SEC_GROUP   | x        | Security group to use               |
| KEY              | x        | Name of the SSH key to use          |
| EXT_NET          | x        | Name of the external network        |
| FLOATING_IP_POOL | x        | Name of the floating IP pool        |
| DNS_SERVER_1     |          | DNS server #1 (defaults to 8.8.8.8) |
| DNS_SERVER_1     |          | DNS server #2 (defaults to 8.8.8.8) |

For default values, see [group_vars/all.yaml](group_vars/all.yaml)

Standard OpenStack environment variables, such as:
- `OS_PROJECT_NAME`
- `OS_DOMAIN_NAME`
- `OS_AUTH_URL`
- `OS_PASSWORD`
- `OS_USERNAME`
