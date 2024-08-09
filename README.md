<h1>Create AWS cloud security using IAM</h1>

This repository contains a walkthrough in using AWS IAM service to control authentication and authorization to use the account's resources. 

Resources used:
- EC2
- IAM

<h1>Objectives</h1>
The project aims to:
<ul>
  <li>Create EC2 instances for production and development.</li>
  <li>Create an IAM policy. This policy should:</li>
    - Allow all EC2 related actions for all resources with the conidition that the resource tag is "development".<br>
    - Allow EC2 describe action for all resources.<br>
    - Deny Deletion and Creation of EC2 tags for all resources.<br>
  <li>Create IAM User Group. Attach the created policy here.</li>
  <li>Create IAM User. Add the user to the newly created user group.</li>
  <li>Test if the access is working as expected.</li>
</ul>
![IAM](https://github.com/user-attachments/assets/1e90020e-de9c-4913-8f22-a4f4f6c78547)
