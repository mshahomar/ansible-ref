# Reference for Ansible

## Get details of previously connected servers in inventory

`ansible all --list-hosts` : shows all hosts  

for a more detail information:

`
ansible all -m gather_facts
`

to limit only to a single host: `ansible all -m gather_facts --limit <IP>`

## Elevated ad-hoc
pass flag --become (or -b) which will be using sudo, and to prompt for password include --ask-become-pass (assumption here: the password is the same for all hosts)

e.g. `ansible all -m apt -a "update_cache" -b --ask-become-pass`

## Using tags with playbook
set ==tags: always== which will always run the tasks, but if you want to limit to specific group of hosts, use ==tags: <name of your tag>==
`ansible-playbook --list-tags site.yml` -- list all tags we have defined in our playbook.

`ansible-playbook --tags ubuntu site.yml` -- targets only tags ubuntu, if no tag ubuntu, it will just skip from executing and no output in stdout.

`ansible-playbook --tags "ubuntu,db" site.yml` -- for more than one tag, enclose it in double quotes and list the tags separated by comma (no space in between!).
