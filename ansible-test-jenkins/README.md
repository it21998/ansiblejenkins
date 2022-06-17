# Prerequisites
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
# Run development environment with Vagrant
* run testing environment
```bash
vagrant plugin install vagrant-hostmanager
cd vagrant
vagrunt up
vagrant ssh-config >> ~/.ssh/config
```
* run a playbook
```bash
ansible-playbook -l database playbooks/database.yml
```
Links:
* [Vagrant Quick start](https://learn.hashicorp.com/collections/vagrant/getting-started)

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


# Ready to run playbooks
```bash
ansible-playbook playbooks/postgres.yml
ansible-playbook playbooks/django-project-install.yml
ansible-playbook playbooks/django2-install.yml
ansible-playbook playbooks/mailhog.yml
```
