# wekan-deployment

Automatically deploy a Wekan instance on DigitalOcean.

## Prerequisites

- DigitalOcean [API key](https://www.digitalocean.com/docs/api/create-personal-access-token/)
- Ansible [installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- Packer [installed](https://www.packer.io/intro/getting-started/install.html)
- Terraform [installed](https://learn.hashicorp.com/terraform/getting-started/install.html)

## Deployment

### Packer
A DigitalOcean API token should be set using the `DIGITALOCEAN_API_TOKEN`
environment variable. This can be overridden at run time if necessary:
	`export DIGITALOCEAN_TOKEN=secret`

Verify if the Packer template validates successfully:
	`packer validate digitalocean-image.json`

Start the initial DigitalOcean droplet creation, provisioning and snapshotting:
	`packer build digitalocean-image.json`
