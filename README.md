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

I successfully installed Virtual Studio Code to serve as an Integrated development environment (IDE)  IMAGE 09

![09](https://user-images.githubusercontent.com/91284177/148757818-545b603c-9aad-4bac-9f89-eb3cbacdba48.png)







