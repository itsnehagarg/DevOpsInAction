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
   ![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/ccab4dc3-6e0d-4725-a396-d29b4452c6f4)

3. One for running the ansible commands & the other one as target server or destination server. Using the Ansible server we will do configurations of destination server.
4. We need to setup password less authentication. So, ansible server can communicate with the other server.

   
```
sudo apt update
sudo apt install ansible
ansible --version
```

4. Lets setup password less authentication.
5. Use the command in Server 1 (Ansible server) :
```
ssh-keygen
```
Two keys get generated: public key and private key.
6. We will go to the path of public key cd /home/ubuntu/.ssh and copy the public key named id_rsa.
7. Now Connect to your 2nd machine(target machine): We will perform ssh-keygen on this server also.
8. Go to the location where the keys got generated.
9. Open the authorizedkeys file using the vi editor.
10. Now paste the public key (id_rsa) which was copied from server 1. This will ensure the authorization of the server 1 on server 2.
![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/adab5d2e-f20b-4e3e-93fc-38216b43a7a5)

11. Let's go back to server 1 and do an ssh to the target server.
```
ssh private_ip_of_target_server
```
Now you can see that we can connect to target server without any password.






#### 🌼References:
https://www.digitalocean.com/community/conceptual-articles/an-introduction-to-configuration-management-with-ansible

https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04








