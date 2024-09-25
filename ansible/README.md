# Ansible docs

# Infra setup from scratch

## Pre-tasks

* Make sure that ansible (>=2.16), ansible-playbook and ansible-galaxy are installed
* Create authkey for Tailscale (needs to be valid for the duration of provisioning)
  - And store it somewhere safe, i.e. `~/.ppmedia_tsauth.key` on the host that does the provisioning
* Get the secret key for the vault and put it in `~/.ppmedia_vault_pass.txt`
  - Doesn't work properly yet, TODO: fix

## Set up the router

TODO

* Reset
* Connect bootstrapper
* Put in base config
* Connect bootstrapper to new port

## Set up bootstrapper

1. Install bootstrapper node with Debian (or Raspberry Pi OS)
2. Add the pubkey for the deploying computer (i.e. yours) to the `authorized_keys` file for root
3. Manually set up Tailscale on the bootstrapper node with 100.111.0.2 as IP
4. Comment out every node but bootstrapper in `hosts`
5. Run `ansible-playbook -l bootstrapper.media.polarparty.no playbooks/site.yml` to put basic config on the bootstrapper ndoe
6. Run `ansible-playbook playbooks/pxe.yml` to set up PXE boot

## Set up nodes

1. Connect node to node network on the router
2. Boot with PXE boot
3. Select Debian with preseed file
4. Input hostname when asked (without domain)
5. Wait until install finishes and reboot
6. Find device in Tailscale and set appropriate tailnet IP

When all nodes are set up/in Tailscale, run `ansible-playbook playbooks/site.yml` to do the rest of the setup.
