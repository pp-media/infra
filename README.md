# infra

> Inspired by https://github.com/FOSDEM/infrastructure/tree/master/ansible

## Set up the vault password

Secrets are encrypted with [ansible-vault](http://docs.ansible.com/ansible/playbooks_vault.html).

To use ansible-vault transparently, create a file with the shared secret and export it via an environment variable.

Ask @kfh on Slack for the secret if you need it :)

    echo "SECRET" > ~/.ppmedia_vault_pass.txt
    export ANSIBLE_VAULT_PASSWORD_FILE=~/.ppmedia_vault_pass.txt

Goals;
1. create a redeployable system that can be used year after year, with low maintenance
2. automate mundane tasks, that may lock up someones pc for hours on end, while enjoyable work can be done, and games can be played!
3. quality of life improvements for media during production hours
4. create a docker or kubernetes system/cluster to automate transcoding
5. create manuals for how to attach our media storage to local machines
6. learn stuff!


what technologies are we considering to leverage?
1. Ansible
2. Docker
3. OME (oven media engine
4. kubernetes (do we need 2 containerized services?)
5. linux is highly considered!
