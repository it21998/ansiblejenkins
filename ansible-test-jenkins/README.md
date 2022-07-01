# Prerequisites
* To run this project we created a jenkins vm in gcloud to access jenkins 
* Created public key for gcloud vm -> azurevm connection
* Installs on gcloud machine that runs the playbooks
* Ansible install
```bash
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible

sudo apt update
sudo apt install ansible
```
* roles install
```bash
ansible-galaxy install geerlingguy.postgresql
ansible-galaxy install jebovic.mailhog
```
* to test if a group of hosts are accesible, run
```bash
ansible -m ping all <group-name>
```
# Possible tweaking code
* hosts.yml
```yaml
deploymentjenkins:
  hosts:
    deploy2:
      ansible_host: 20.254.97.185
      ansible_port: 22
      ansible_ssh_user: jenkins  
```
# Open ports on azure
* 8000
* 9000
* 5000
* 8025

# Possible error fixes for ansible-temporary-files
```bash
apt install sudo
sudo apt-get update -y
sudo apt-get install -y acl
```

# Access
```bash
http://20.254.97.185:8000/    #admin
http://20.254.97.185:9000/    #system
http://20.254.97.185:8025/    #mailhog
```
