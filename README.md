# PROJECT-11
ANSIBLE-CONFIG-MGT


**INSTALL AND CONFIGURE ANSIBLE ON EC2 INSTANCE**
****
I will install and configure Ansible client to act as a Jump Server/Bastion Host and also create a simple Ansible playbook to automate servers configuration. This is represented below. IMAGE 01

![01](https://user-images.githubusercontent.com/91284177/148755626-c552ec4a-3d13-4abe-9e8b-e30f0ba48e69.png)

I updated Name tag on my Jenkins EC2 Instance to Jenkins-Ansible. I will use this server to run playbooks.
In my GitHub account, I created a new repository and name it ansible-config-mgt. IMAGE 02
![02](https://user-images.githubusercontent.com/91284177/148755963-db0713db-bea8-491e-b53e-71869470415c.png)


I Installed Ansible using <sudo apt update -y && sudo apt install ansible> and checked if Ansible was up and running. IMAGE 03
![03](https://user-images.githubusercontent.com/91284177/148756301-d2ba743b-0881-4aa3-ae02-d2706b536c6a.png)

I configured Jenkins build job to save my repository content every time I changed it. IMAGE 04
![04](https://user-images.githubusercontent.com/91284177/148756605-2ad971db-6797-4d9d-a01f-75f3aa9ba94d.png)

I created a new Freestyle project ansible in Jenkins and pointed it to my ‘ansible-config-mgt’ repository. Also configured Webhook in GitHub and set webhook to trigger ansible build. IMAGE 05
![05](https://user-images.githubusercontent.com/91284177/148756791-341b7149-a589-498b-ba89-c63aee85a982.png)


Configured a Post-build job to save all (**) this is is necessary for github webhook to automatically push codes updatated/edited/added to jenkins-ansible. IMAGE 06

![06](https://user-images.githubusercontent.com/91284177/148757348-17081525-0352-4ad4-bd31-4d5d12eefab8.png)

I Tested the setup by making some change in README.MD file in master branch and made sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder. IMAGES 07 & 08
![07](https://user-images.githubusercontent.com/91284177/148757574-d9b85903-5bcb-4012-963c-25401a920cfa.png)

![08](https://user-images.githubusercontent.com/91284177/148757553-15c419c2-065c-4b63-9748-291a539ef3dc.png)

**Step 2 – Prepare your development environment using Visual Studio Code**
Tested my setup by making some change in README.MD file in master branch and made sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/ IMAGE 09
![09](https://user-images.githubusercontent.com/91284177/149334232-ae53c845-3019-4097-ae26-daf50aa277b5.png)

I successfully installed Virtual Studio Code to serve as an Integrated development environment (IDE)  IMAGE 10 comfirmed this.

![10](https://user-images.githubusercontent.com/91284177/149333901-a3f0587e-e079-4b88-a7c8-b27ea4ebfbde.png)

STARTED ANSIBLE DEVELOPMENT
In my ansible-config-mgt GitHub repository, I created a new branch that will be used for development of a new feature. named it 'Prj-11' IMAGE11

![11](https://user-images.githubusercontent.com/91284177/149837687-a2b94851-467c-4c61-a54b-7c6ed8650b06.png)
I created two directories and named them Playbook (it was used to store all my playbook files.) and Inventory (it was used to keep my hosts organised.)
Within the playbooks folder, I created my first playbook, and name it common.yml

Within the inventory folder, I create an inventory file (.yml) for each environment (Development, Staging Testing and Production) i.e dev, staging, uat, and prod respectively. Also Updated my inventory/dev.yml file with this snippet of code: as seen in IMAGE 12

![12](https://user-images.githubusercontent.com/91284177/149838491-8a8b3455-c792-4ad3-819e-f026b9c45715.png)

Step 4 – #Set up an Ansible Inventory#

In common.yml playbook i wrote configuration for repeatable, re-usable, and multi-machine tasks that is common to systems within the infrastructure. Updated my playbooks/common.yml file IMAGE 13

![13](https://user-images.githubusercontent.com/91284177/149839450-6a257263-3111-4ac1-b46e-76651fe469dc.png)

Commited the changes to file to my prj-11 branch accordingly. IMAGE 14

![14](https://user-images.githubusercontent.com/91284177/149839524-c62a17a4-f905-436c-afd1-26fef6df162a.png)
Pushed the changes to the brach prj-11. IMAGE 15

![15](https://user-images.githubusercontent.com/91284177/149939384-fb99d127-880a-4fbb-9836-6f4f7ee8a1c0.png)
I pushed the udtated brach to the mian repo in github, the processes is represented IMAGES 16-21
![16](https://user-images.githubusercontent.com/91284177/149974976-b6baa192-6edd-45b3-ad76-64f3cefc562f.png)
![17](htt![18](https://user-images.githubusercontent.com/91284177/149975040-12908189-7b22-4ef6-8f22-bc2b6cf141df.png)
![18](https://user-images.githubusercontent.com/91284177/149975075-153d519a-0dd6-4c6a-bd4b-240e8bbbcbbc.png)
![19](https://user-images.githubusercontent.com/91284177/149975118-47d712d7-1def-4633-833a-88cad0ecb904.png)
![20](https://user-images.githubusercontent.com/91284177/149975147-b9011f5f-4028-409a-ac41-8ff25e459f3a.png)
![21](https://user-images.githubusercontent.com/91284177/149975173-48d754da-dbc8-4afe-9ede-3aa48b978d7f.png)

I comfirmed Jenkins pushed the updated messages in inventory to my ansible-jenkins server. IMAGE 22-23
![22](https://user-images.githubusercontent.com/91284177/149975667-b355ca21-5c8d-4a8e-ba33-2af68de48a6a.png)
![23](https://user-images.githubusercontent.com/91284177/149975720-a7dfbe31-51cc-4f41-b293-8db05743757e.png)














