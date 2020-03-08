# FUll-On 

## File structure
AWS_Ansible
    .
    ├── group_vars
    │   ├── all --- pass.yml      # contains IAM user credentials
    │               
    │  
    └── playbook.yml       #the playbook  

## Pre-requisits
- Ansible
- AWS user
- AWS IAM user 
- Ansible vault 
  

## Credentials
To create the Ansible perform the following :
`ansible-vault create group_vars/all/pass.yml`
after its created enter the following:
` 
ec2_access_key: <access key> 
                                     
ec2_secret_key: <secret key>
`

## The playbook 

to run the playbook: 
`ansible-playbook playbook.yml --ask-vault-pass`

- the playbook creates and configures the keypair used to connect to the remote ec2 server (no need to worry about keypairs)
- creates both the ec2 instance and its security group (enables connection on ports 80 & 22 )
- install docker on the remote server.
- install pip docker module.
- creates network and runs containers. (i already pushed the images to dockerhub. you can see the dockerfiles in the added directories)

