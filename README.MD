# Ansible Playbooks

*by Shivan Sivakumaran*

## About

This is for my self-hosted projects that sit on the domain shivan.xyz.

## How to use?

The directory structure
```
deploy.yml
deploy
```

1. Create a directory under `deploy/` (e.g. `optomcalc`).
2. Inside the new directory, include subdirectories `files` and `main`.
3. `files/` will contain any unique source code
4. `main/` will contain `main.yml` files to run the playbook
5. create an nginx config files (e.g. `optomcalc.shivan.xyz`)
6. Add the playbook to the `deploy.yml` master play book.

## TODOs

1. Create a 'template' for a project so `cp` can be applied instead of making new directorie and files. 
2. Create a playbook for `optomcalc`
