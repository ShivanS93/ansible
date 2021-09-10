# Ansible Playbooks

*by Shivan Sivakumaran*

## About

This uses [Ansible](https://docs.ansible.com/), a useful automation tool. This allows me to work on my code locally and then implemented these changes onto
a live server.

This is for my self-hosted projects that sit on the domain [shivan.xyz](http://shivan.xyz).

## Current apps

- [OptomCalc](https://optomcalc.shivan.xyz)
- [TubeStats](https://tubestats.shivan.xyz)
- [HowGoodIsLasha](https://lasha.shivan.xyz)

## How to use?

0. Ansible uses ssh configuation to connect to the server. Ensure the config is set up:
	```
	Host shivan.xyz
	IdentityFile ~/.ssh/path/to/key
	IdentitiesOnly yes
	User <user>
	Port <port number>
	```
1. Refer to the directory structure below. First, copy an app directory.
	```
	cp -r ./deploy/example-app ./deploy/new-app
	```
2. `files/` will contain any unique source code (e.g. `.env` file). 
3. `main/` will contain `main.yml`, which is the playbook to run the app including setting up `nginx`. 
5. `templates/` contains the `nginx` config file. **Ensure to rename the templates file** (e.g. `newapp.shivan.xyz`).
6. Add the new playbook to the `deploy.yml` master playbook.
6. Run the play book.
	```
	pipenv run ansible-playbook deploy-all.yml -i hosts -K
	```
7. To run just one app.
	```
	pipenv run ansible-playbook deploy-app1.yml -i hosts -K
	```


The directory structure of this app.
```
├── ansible.cfg
├── deploy
│   ├── common	# common tasks to run (e.g. update server)
│   │   └── tasks
│   │       └── main.yml
│   └── example-app	# app related automation
│       ├── files
│ 	│   └── .env 
│       ├── tasks
│       │   └── main.yml
│       └── templates
│           └── subdomain.shivan.xyz
├── deploy-all.yml 	# runs all apps
├── deploy-app1.yml	# installs all apps
├── hosts
├── LICENSE
├── Pipfile
├── Pipfile.lock
└── README.MD
```

## Feedback

Any feedback is appreciated.
