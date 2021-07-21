# Ansible Playbooks

*by Shivan Sivakumaran*

## About

This is for my self-hosted projects that sit on the domain shivan.xyz.

## How to use?

1. Refer to the directory structure below. First, copy an app directory.
	e.g. `cp -r ./deploy/example-app ./deploy/new-app`
2. `files/` will contain any unique source code (e.g. `.env` file). 
3. `main/` will contain `main.yml`, which is the playbook to run the app including setting up `nginx`. 
5. `templates/` contains the `nginx` config file. *Ensure to rename the templates file* (e.g. `newapp.shivan.xyz`).
6. Add the new playbook to the `deploy.yml` master playbook.
6. Run the play book.
	```
		pipenv run ansible-playbook deploy.yml -i hosts -K
	```



The directory structure of this app.
```
├── ansible.cfg
├── deploy
│   ├── common
│   │   └── update_server
│   │       └── main.yml
│   └── example-app
│       ├── files
│ 	│   └── .env 
│       ├── tasks
│       │   └── main.yml
│       └── templates
│           └── subdomain.shivan.xyz
├── deploy.yml
├── hosts
├── LICENSE
├── Pipfile
├── Pipfile.lock
└── README.MD
```

## TODOs

1. Create a 'template' for a project so `cp` can be applied instead of making new directorie and files. 
2. Create a playbook for `optomcalc`
