<h1>Create AWS cloud security using IAM</h1>

This repository contains a walkthrough in using AWS IAM service to control authentication and authorization to use the account's resources. 

Resources used:
- EC2
- IAM

<h1>Objectives</h1>
The project aims to:
<ul>
  <li>Create EC2 instances for production and development.</li>
  <li>Create an IAM policy. This policy should:
    <li>Allow all EC2 related actions for all resources with the conidition that the resource tag is "development".</li>
    <li>Allow EC2 describe action for all resources.</li>
    <li>Deny Deletion and Creation of EC2 tags for all resources.</li>
  </li>
</ul>
