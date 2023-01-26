# Reference for Ansible

## Get details of previously connected servers in inventory

`ansible all --list-hosts` shows all hosts  

for a more detail information:

`
ansible all -m gather_facts
`

to limit only to a single host: `ansible all -m gather_facts --limit <IP>`
