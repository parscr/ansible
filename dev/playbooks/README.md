##On control host, login as ansible and create ssh-key (If it does not already exist)

$ ssh-keygen

## run playbook ; enter root password!

$ ansible-playbook -i hosts  create-ansible-user.yaml --ask-pass
SSH password:


## Test login to the managed host as ansible it should not ask for a password! 
## test you have sudo access with no password required

$ ssh -X ansible@managedhost

$ whoami
ansible

$ sudo whoami
root

## On control host ping managedhost

ansible -i hosts -m ping
ansible -i /home/ansible/server-playbooks/hosts neil -m ping 
