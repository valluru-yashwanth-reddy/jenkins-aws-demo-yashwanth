# jenkins-aws-demo-yashwanth



----> first we create two EC2 instances using the Terraform AWS provider and naming them as (jenkins-master) and (jenkins-agent-1)
----> For the master  EC2 instance (jenkins-master) we have to set inbound rules which allows SSH, HTTP, HTTPS, and also a custom TCP port 8080 this for running Jenkins.
----> For the agent EC2 instance (jenkins-agent-1) for this we only need to allow SSH access.
----> Once this is done then we SSH into both the master(jenkins-master) and agent (jenkins-agent-1) instances using their public IP addresses in two separate terminal windows.
----> I am using Ubuntu for both instances because it is easier to work with for this setup.
----> After getting into the instances then we need to install Jenkins on the master so we can access the Jenkins and we also install Node.js because the application we are going to build is a Node.js app. Along with that we also install Docker because it is useful for container-based builds and deployments.
----> Next we need to generate the public and private SSH keys on the agent. 
----> Then we copy the agent public key to the master so that the master can connect to the agent.
----> After setting up the key connection we open the Jenkins dashboard by entering the master public IP (jenkins-master) followed by port 8080 in the browser.
----> After Jenkins is ready we create a new credential in Jenkins which we will use to connect to GitHub or for SSH access.
----> Once that is done then we go to the Jenkins and add a new node with a label like ubuntu.
----> This will be our agent node that Jenkins uses to run jobs. 
----> Now we open GitHub and create a new repository where we push our Node.js app files like app.js and package.json and Jenkinsfile to the repo which defines the pipeline steps for Jenkins. 
----> After pushing all the files then we go back to Jenkins to create a new pipeline job.
----> Then link it to our GitHub repo and then build it.

![Screenshot (38)](https://github.com/user-attachments/assets/167c1445-423d-40ba-998c-5fe16d046120)
![Screenshot (37)](https://github.com/user-attachments/assets/3b8f9744-554c-4dc1-929c-96f7f3286224)

![Screenshot 2025-06-23 093929](https://github.com/user-attachments/assets/5a52c934-5766-417d-8193-524b0feeefb5)
![Screenshot 2025-06-23 092755](https://github.com/user-attachments/assets/da2fac27-ac80-42ac-8f8d-dcd95b3a78e8)
![Screenshot 2025-06-23 092016](https://github.com/user-attachments/assets/04b305c5-3c33-4077-9958-e59a32cf5b56)
![Screenshot (51) (1)](https://github.com/user-attachments/assets/18fc1916-ad1a-4b13-977f-58204426d4e2)



