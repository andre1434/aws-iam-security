<h1>Create AWS cloud security using IAM</h1>

This repository contains a walkthrough in using AWS IAM service to control authentication and authorization to use the account's resources. 

Resources used:
- EC2
- IAM
<br><br>Region: us-west-2 (Oregon)

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
  <img src="/AWS IAM Security/IAM.jpg" alt="Architecture">

<h2>Stage 1: Create EC2 Instances</h2>
<p>The creation of the 2 EC2 instances is for the purpose of differentiating the effects of the policy to be created.</p>
When creating the EC2 instance, add an additional tag with Key = "<b>Env</b>". Value to be input will be <b>"production"</b> for production environment EC2 instance, and <b>"development"</b> for development environment EC2 instance.<br><br>

  <img src="AWS IAM Security/Creating EC2 Instances.jpg" alt="EC2">

<br>
The tag is needed for the first policy requirement.

<h2>Stage 2: Create an IAM Policy</h2>
For this project, we need to create an IAM policy to:<br>
    - Allow all EC2 related actions for all resources with the conidition that the resource tag is "development".<br>
    - Allow EC2 describe action for all resources.<br>
    - Deny Deletion and Creation of EC2 tags for all resources.<br><br>
This can be done through AWS IAM, under Policies section.<br>
JSON file can be checked <a href= "AWS IAM Security/IAM Policy">here</a>.
<br><br>

  <img src="AWS IAM Security/JSON policy.jpg" alt="IAM Policy">

<h2>Stage 3: Create IAM User Group</h2>
AWS IAM user group can be created in IAM service, under User groups section.<br>
We also need to attach the created policy to this user group.<br><br>
<b>Why do we need to create user groups?</b> In a real world scenario, there are different departments that handle different tasks. However, each user per department would require the same permissions. For this reason, it is easier and more efficient to group each user using user groups based on their department.<br>
For this project, we assume that the new IAM user will be onboarded and added to a user group.

<h2>Stage 4: Creating IAM User</h2>
We need to create an IAM user and add the user to the created user group. This can be done through AWS IAM, under Users.<br>
<i>Note: Check the <b>Provide user access to the AWS Management Console</b></i> <br><br>
We then add the user to the user group.<br>

  <img src="AWS IAM Security/new user creation.jpg" alt="IAM user">

Save the login details.

<h2>Stage 5: Testing</h2>
To test if the policy is correct and working, we will need to login the IAM user created.
<br>
Proceed testing as follows:<br>
<ul>
  <li>Go to EC2, then instances</li>
  <li>Try to stop Production EC2 instance</li>
  Expectation is that there would be an authorization error. Reason is that the policy only allowed the action for EC2 instances with "development" tag.
  <img src="AWS IAM Security/error message ec2 prod.jpg" alt="Prod error"><br><br>
  <li>Try to stop Development EC2 instance</li>
  Expectation is that the action would be successful as the policy allows this.
  <img src="AWS IAM Security/success stop ec2 dev.jpg" alt="Prod error">
</ul>
<br><br>
Another way in testing the policy is by using the Policy Simulator. This, for me, is an easier and a move convenient way to test the policy if used correctly.<br>
This can be accessed through the IAM dashboard section.<br><br>
<img src="AWS IAM Security/Using Policy Simulator.jpg" alt="Policy Simulator"><br><br>

<h3>## Credits ##</h3>
Project was originally authored by <a href="https://community.nextwork.org/home">Nextwork</a>.
