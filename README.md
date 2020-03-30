**ANSIBLE ROLE**

Roles provide a framework for fully independent, or interdependent collections of variables, tasks, files, templates, and modules. In Ansible, the role is the primary mechanism for breaking a playbook into multiple files. This simplifies writing complex playbooks, and it makes them easier to reuse.

**ANSIBLE GALAXY**

Ansible has a nice tool named ansible-galaxy which is used to perform various role related operations. One of these operations named ansible-galaxy init is to setup the predefined Ansible role directory structure for your Ansible projects.
Inside the roles directory you will execute the ansible-galaxy command with the init argument and the Ansible role name you wish to develop.

```bash
[jo@ansibleserver roles]$ ansible-galaxy init <name of the ansible role>

```
After you execute the ansible-galaxy init command you will see the distinct, universal, predefined directory structure of the Ansible role you just created. That directory structure will be:

```bash
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── README.md
├── tasks
│   └── main.yml
├── templates
├── tests
│   ├── inventory
│   └── test.yml
└── vars
    └── main.yml
```

In our case, aws-role is the role directory which we created and this role directory includes the below structures:

```bash
.
├── ansible-aws.yml
└── aws-role
    ├── defaults
    │   └── main.yml
    ├── files
    ├── handlers
    │   └── main.yml
    ├── meta
    │   └── main.yml
    ├── README.md
    ├── tasks
    │   ├── asgcnf.yml
    │   ├── launchcnf.yml
    │   ├── loadbalancer.yml
    │   ├── main.yml
    │   └── targetgp.yml
    ├── templates
    ├── tests
    │   ├── inventory
    │   └── test.yml
    └── vars
        ├── creds.yml
        └── main.yml

```
**Ansible Vault for AWS Credentials**

Ansible Vault is a feature of ansible that allows you to keep sensitive data such as passwords or keys in encrypted files, rather than as plaintext in playbooks or roles. These vault files can then be distributed or placed in source control.

Steps for creating Ansible-Vault file:

- Create a vault credentials file named <filename.yml> using the command 'ansible-vault create <filename.yml>'
- Enter a password for the vaultfile we created.
- Don't forgot to note down the password, we need the password to run our playbook file.

- Insert AWS Credentials into the file.The file be like;
```bash
---
VAULT_AWS_ACCESS_KEY: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
VAULT_AWS_SECRET_KEY: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```


