# 🌻Configuration Management using Ansible

Some operations that needs to be performed: 
-Upgrades
-Installation of softwares
-Secure patches

Earlier scripts were written to perform these actions on the servers. If it is Windows machine then powershell scripts, linux machine then bash/ shell scripts needs to be written.

Now everything is getting moved to cloud. Number of servers have increased alot.

In Configuration Management we have many popular tools: Chef, Puppet, Ansible, Salt

### 🌻 Puppet: 
- pull-mechanism,
- master slave architecture,
- puppet language
  
### 🌻 Ansible: 
Ansible is a modern configuration management tool that facilitates the task of setting up and maintaining remote servers, with a minimalist design intended to get users up and running quickly.
- push mechanism,
- uses agent less model.
- Support for Windows/ Linux is good with Ansible,
- YAML files are used in Ansible.

#### 🌼Disadvantages of Ansible:
1. Debugging needs to be improved
2. Performance needs to be improved
3. Windows support of ansible needs to be improved

🌼Interview questions:
1. Ansible supports both Linux & Windows.
For Linux it uses SSH protocol.
For Windows it uses WinRM protocol.
2. Diff between Puppet/ Chef & Ansible.
3. Ansible is pull or push mechanism.
4. Which programming language is used to write Ansible playbooks? YAML
5. Ansible supports every cloud provider?- Cloud Provider is not a concern for ansible. Main things are: IP address, SSH access to the machine, Ansible hosts can access the machines, are they SSH enabled.

### Ansible installation on EC2:

1. We will create 2 EC2 servers.
2. One for running the ansible commands & the other one as target server or destination server. Using the Ansible server we will do configurations of destination server.
3. We need to setup password less authentication. So, ansible server can communicate with the other server.

   
```
sudo apt update
sudo apt install ansible
ansible --version
```

#### 🌼References:
https://www.digitalocean.com/community/conceptual-articles/an-introduction-to-configuration-management-with-ansible

https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04








