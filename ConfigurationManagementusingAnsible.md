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
5. Use the command in Server 1 (Ansible server) :Two keys get generated: public key and private key.
```
ssh-keygen
```

6.  We will go to the path of public key cd /home/ubuntu/.ssh and copy the public key named id_rsa.
7.  Now Connect to your 2nd machine(target machine): We will perform ssh-keygen on this server also.
8.  Go to the location where the keys got generated.
9.  Open the authorizedkeys file using the vi editor.
10.  Now paste the public key (id_rsa) which was copied from server 1. This will ensure the authorization of the server 1 on server 2.
11.  Let's go back to server 1 and do an ssh to the target server.
```
ssh private_ip_of_target_server
```
Now you can see that we can connect to target server without any password.

12. We can also execute Ansible adhoc commands.
    Inventory stores the IP addesses of the target servers.The default location for the inventory file is /etc/ansible/hosts. You can also create project-specific inventory files in alternate locations. The inventory file can list individual hosts or user-defined groups of hosts.
```
ansible -i inventory private_IP_address_of_target_server
```
```
ansible -i inventory all
```
all above means all the IP addresses in the inventory file.

1.1 Created a inventory file
1.2 Added the private IP address of the target server to this file.

![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/94ab1770-4170-4930-af91-0529e93cd4ce)

1.3 Execute the below command:
```
ansible -i inventory all -m "sheell" -a "touch devopsclass"
```
![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/7aace5e8-5716-4452-a9fe-027bef48261e)

1.4 After executing the command we will go back to the target server and check if the file is created.

![image](https://github.com/itsnehagarg/DevOpsInAction/assets/20385826/9e7907b8-649f-477c-be84-bb84928bade7)

13. 
14. Now we will write Ansible playbooks.Ansible Playbooks offer a repeatable, reusable, simple configuration management and multi-machine deployment system, one that is well suited to deploying complex applications. 




#### 🌼References:
https://www.digitalocean.com/community/conceptual-articles/an-introduction-to-configuration-management-with-ansible

https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-20-04








