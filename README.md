<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Item 1: Configure Roles
- Item 2: Configure Departments
- Item 3: Configure Teams
- Item 4: Allow Anyone to Create Tickets
- Item 5: Configure Agents (employees)
- Item 6: Configure Users (customers)
- Item 7: Configure SLA
- Item 8: Configure Help Topics

<h2>Prerequisites</h2>

In the previous project, we installed osTicket and items to allow osTicket to run effectively. In order to do this project, osTicket must already be installed. Link to installing osTicket: [LINKKKKKK]

<h2>Configuration Steps</h2>

<h3>Access osTicket</h3>

1. Navigate to Microsoft Azure portal > select ‘Virtual Machines’ > select ‘VM-osTicket > copy the Public IP address (Example: 20.14.93.5)
2. Open Microsoft Remote Connection (for Windows) or launch Microsoft Remote Desktop app (for MacOS) > paste Public IP address > log in with the username/password created in step 1 of this lab: [LINKKKK]
3. Navigate to URL for admin login:  http://localhost/osTicket/scp/login.php
4. Log in with the admin username & password created in step 3 of the previous lab. (Example: darin_admin)

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Admin vs Agent Portal</h3>

<p>Within osTicket, there is both an Admin Portal and an Agent Portal. We're going to be working with both portals.</p>

<p>The Admin Portal is designed for administrators to manage the osTicket ticketing system. It provides access to various administrative functions such as configuring support queues, managing staff members and permissions, and customizing system settings to efficiently handle and resolve customer support tickets.</p>

<p>The agent portal within osTicket is a web-based interface designed for support agents or staff members. It allows agents to access and manage support tickets assigned to them, communicate with customers, update ticket statuses, and collaborate with other agents to provide timely and effective customer support within the osTicket ticketing system.</p>

<br>

<h3>Item 1: Configure Roles</h3>

<strong>What are roles in osTicket?</strong>

<p>According to osTicket:</p> <br>
  <p>"Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments." -osTicket</p>
  
  osTicket documentation on Roles: https://docs.osticket.com/en/latest/Admin/Agents/Roles.html
  
  <p>We’re going to create a role called ‘Supreme Admin' and anyone with this title of Supreme Admin has access to do literally anything.</p>
  
  1. Navigate to 'Admin Panel' within osTicket > Select 'Agents' > Select 'Roles' > Select 'Add a New Role'
  2. Give the name: 'Supreme Admin' > Navigate to ‘Permissions’ tab
  3. For the fun of it, we’re going to allow them to do everything: Check all the boxes [X] under the ‘Tickets’, ‘Tabs’, and ‘Knowledge Base’ > select 'Add Role'

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Configure Departments</h3>















<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


