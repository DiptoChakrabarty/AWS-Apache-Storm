# AWS-Apache-Storm

## About the Project

Setup a full Apache Storm Cluster in AWS to perform realtime computation using Ansible. Edit configuration required by user and run playbook.
Ansible will take care of all setup , define number of worker and nimbus nodes required and additional configuration in roles developed.

## How to Run 

- Add you aws pem key to ssh
```sh
  ssh-add <pem kay name>


  change  private_key_file  path in ansible.cfg with your private key path

```

- Activate virtualenvironment first
```sh
source /venv/bin/activate
```
- Add python interpreter path in hosts file
```sh
which python3

add output in python_interpreter in hosts file

Also install boto3 and boto
```

- First add your keys in vault file
```sh
ansible-vault edit key.yml

password: storm

Add AWS keys 

Also add security group name you want

Key is to be present from before
```
- Run playbook using

```sh
ansible-playbook  --vault-password-file=".password" -i ./hosts ec2.yml
```

## Description of Roles
```sh
- There are two roles present
  * storm
  * zookeeper
- Nimbus node both the roles are utilised
- Worker nodes only zookeeper role is used
```

<img src="images/storm.png">




<img src="images/svc.png">
