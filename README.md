<h1>Create AWS cloud security using IAM</h1>

This repository contains a walkthrough in using AWS IAM service to control authentication and authorization to use the account's resources. 

Resources used:
- EC2
- IAM
Region: us-west-2 (Oregon)

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
<div style="align-items: center;">
  <img src="/AWS IAM Security/IAM.jpg" alt="My Project Logo">
</div>

<h2>Stage 1: Create EC2 Instances</h2>
<p>The creation of the 2 EC2 instances is for the purpose of differentiating the effects of the policy to be created.</p>
When creating the EC2 instance, add an additional tag with Key = "<b>Env</b>". Value to be input will be <b>"production"</b> for production environment EC2 instance, and <b>"development"</b> for development environment EC2 instance.<br><br>
<div style="align-items: center;">
  <img src="AWS IAM Security/Creating EC2 Instances.jpg" alt="My Project Logo">
</div>
<br>
Reason: 
