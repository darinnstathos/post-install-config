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

<p>According to osTicket:</p>
  <p>"Roles are the permissions granted to Agents per Department that they have access to. Each Role has a set of permissions that can be checked/unchecked for agents given that Role in association with a Department they have access to. An unlimited number of roles can be created and assigned to Agents with access to various departments." -osTicket</p>
  
  osTicket documentation on Roles: https://docs.osticket.com/en/latest/Admin/Agents/Roles.html
  
  <p>We’re going to create a role called ‘Supreme Admin' and anyone with this title of Supreme Admin has access to do literally anything.</p>
  
  1. Navigate to 'Admin Panel' within osTicket > Select 'Agents' > Select 'Roles' > Select 'Add a New Role'
  2. Give the name: 'Supreme Admin' > Navigate to ‘Permissions’ tab
  3. For the fun of it, we’re going to allow them to do everything: Check all the boxes [X] under the ‘Tickets’, ‘Tabs’, and ‘Knowledge Base’ > select 'Add Role'

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 2: Configure Departments</h3>

<Strong>What are Departments in osTicket?</strong>

<p>In osTicket, departments are organizational units or groups that are created to manage and categorize support tickets based on different criteria. They represent different areas or teams within an organization that handle specific types of inquiries or provide support for distinct products or services. Tickets can be assigned to specific departments, allowing for efficient routing and distribution of tickets to the appropriate teams or individuals for effective resolution.</p>

osTicket documentation on Departments: https://docs.osticket.com/en/latest/Admin/Agents/Departments.html

1. Navigate to Admin Panel > Select 'Agents' > Select 'Departments' > Select 'Add a New Department'
2. Give the name: 'System Administrators' 
3. There’s many settings inside of here, including SLA. We haven’t configured SLA yet so we’ll leave these default settings. At the bottom of the screen, select “Create Dept”

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 3: Configure Teams</h3>

<Strong>What are Teams in osTicket?</strong>

<p>According to osTicket, "Teams allow you to pull Agents from different Departments and organize them to handle a specific issue or user via a Help Topic or Ticket Filter." Essentially, if you have many Departments and you want to pool the best technicians from each Department to solve a particular issue, you can do so by creating a Team within osTicket.</p>

osTicket documentation on Teams: https://docs.osticket.com/en/latest/Admin/Agents/Teams.html

1. Navigate to 'Admin Panel' > Select 'Agents' > Select 'Teams' > Select 'Add a New Team'
2. We’re going to create a Level I Support and a Level II Support. Since Level I was automatically generated, we’re going to create Level II. We can add ourselves as part of the team for fun. 

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 4: Allow Anyone to Create Tickets</h3>

<p>We're going to alter the settings so that anyone can create a ticket, even anonymously. No one requires special authentication or permissions to create a ticket.</p>

1. Navigate to 'Admin Panel' > select 'Settings' > select 'User'
2. Make the sure the following is unchecked: [ ] “Require registration and login to create tickets”

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 5: Configure Agents (employees)</h3>

<strong>What are Agents in osTicket?</strong>

<p>According to osTicket, "Agents are given access to the help desk with the intent to respond and resolve the tickets." Agents are essentially the front-line employees/workers that solve technical issues and answer tickets.</p>

osTicket documentation on Agents: https://docs.osticket.com/en/latest/Admin/Agents/Agents.html

1. Navigate to 'Admin Panel' > select 'Agents' > select 'Add a New Agent'
2. For example purposes:

- Name: Jane Doe
- Email: janedoe@osticket.com
- username: jane.doe

3. Password setting: 

- select 'Set Password' > Uncheck [ ] ‘Send the agent a password reset email’
- set password: 'Password1' > Uncheck [ ]  ‘Require password change at next login’ > select ‘Set’

4. Navigate to other tabs > 'Access' > Department: 'System Administrators' & Role: 'Supreme Admin' & Extended Access: 'Level II Support' > select 'Create' 

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

5. Navigate to 'Admin Panel' > select 'Agents' > select 'Add a New Agent'
6. For example purposes:

- Name: John Doe
- Email: johnedoe@osticket.com
- username: john.doe


7. Password setting:

- select 'Set Password' > Uncheck [ ] ‘Send the agent a password reset email’
- set password: 'Password1' > Uncheck [ ] ‘Require password change at next login’ > select ‘Set’

8. Navigate to other tabs > 'Access' > Department: 'Support' & Role: 'View Only' & Extended Access: 'Support' > select 'Create'

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 6: Configure Users (customers)</h3>

<Strong>What are Users?</strong>

<p>According to osTicket, "Users are the ticket owners of the tickets in the help desk. When a ticket is created in the help desk, the user is associated with their email address in the User Directory of the help desk." Users are the people who are experienching technical difficulties and require assistance from agents.</p>

osTicket documentation on Users: https://docs.osticket.com/en/latest/Agent/Users/User%20Directory.html

1. Navigate to 'Agent Portal'
2. Select 'Users' > Select 'Add a New User'
3. For example purposes:

- Email: karen@osticket.com
- Name: Karen Karen

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

4. Navigate back to 'Users' > Select 'Add a New User'
5. For example purposes:

- Email: ken@osticket.com
- Name: Ken Ken

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 7: Configure SLA</h3>

<Strong>What are SLAs?</strong>

<p>SLA stands for Service Level Agreement. They are meant to outline the agreed-upon levels of service that an IT department or service provider commits to deliver to its customers or end-users. These agreements typically cover areas such as response times, uptime, availability, resolution times, and other performance metrics, ensuring that IT services align with business needs and expectations. SLAs in IT help establish accountability, define service quality standards, and provide a basis for measuring and improving IT service delivery.</p>

<p>According to osTicket, "SLA Plans or Service Level Agreements, are unlimited in osTicket. The purpose of the SLA Plan is to provide a length of time in which the help desk Administrator expects tickets to be closed."</p>
  
  osTicket documentation on SLAs: https://docs.osticket.com/en/latest/Admin/Manage/SLA%20Plans.html
  
  1. Navigate to 'Admin Panel' > select 'Manage' > select 'SLA' > select 'Add a New SLA Plan'
  2. Name: 'SEV-A'

<p>In this example, SEV-A is meant to symbolize a top-priority SLA ticket that has significant business impact if not resolved. An example of a SEV-A ticket would be the entire western region's computers going down or a malware attack leaking user and company private information.</p>

- Time period: '24/7'

<p>This means that this ticket should be solved as soon as possible within the time scope set in the next section. This means that is a ticket comes in even on the weekend, it must be resolved within the time frame created below.</p>

- Hour setting: '1 hour'

<p>1 hour to solve a ticket is highly unreasonable. However, in this example, it's meant to depict how soon the ticket should be resolved or the time span granted to resolve the ticket. Since SEV-A is the most crucial type of ticket, it should be solved as soon as possible. Thus, if a SEV-A ticket came in Saturday morning 8am, it should be resolved by Saturday morning 9am.</p>

- select 'Add Plan'

3. Select 'Add new SLA Plan' 
4. Name: 'SEV-B'

- Time period: '24/7'
- Hour setting: '4 hours'

<p>SEV-B is similar to SEV-A. It has medium to high priority. In this example, due to the 24/7 setting, if a ticket came in even on the weekend such as Saturday afternoon 12pm, it should be resolved by Saturday afternoon 4pm.</p>

- select 'Add Plan'

5. Select 'Add new SLA Plan'
6. Name: 'SEV-C'

- Time period: '8 hours, Monday-Friday (normal business days)
- Hour setting: '8 hours'
  
<p>This is an example of a ticket that is less urgent. If a ticket came in on the weekend, it wouldn't have to be resolved until the following business day. If a ticket came in Monday afternoon at 4pm, and the office closes at 5pm, then there'd be 7 hours remaining the following business day to resolve the ticket.</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br>

<h3>Item 8: Configure Help Topics</h3>

<strong>What are Help Topics?</Strong>

<p>Help Topics are essentially common issues that may arise. Help Topics are created to help end-users/customers communicate the technical difficulties they're facing. According to osTicket, "Help Topics will help streamline your end-user’s help desk experience to ensure proper assignment and prompt response to the ticket...Help Topics will determine what Department the ticket is routed to which will determine which Agents have access to the ticket. The Help Topic also can determine other configurations of the ticket, such as the ticket’s SLA (or Service Level Agreement) and priority of a ticket, i.e. Emergency to Low."
  
  osTicket documentation on Help Topics: https://docs.osticket.com/en/latest/Admin/Manage/Help%20Topic.html
  
  <p>Karen and Ken, the users we just created, can choose what they need help with when filling out tickets on their end.</p>
  
  1. Navigate to 'Admin Panel' > select 'Manage' > select 'Help Topics' > select 'Add a New Help Topic'
  2. We will create the following Help Topics, leave all default settings:

- Business Critical Outage
- Personal Computer Issues
- Equipment Request
- Password Reset

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>Side note: It's possible to do email configuration inside of osTicket so that users can send an email and/or fill out a form. Doing so will automatically generate a ticket for Agents to access/answer. However, that won't be covered in this project.</p>

<p>Now that we have installed osTicket and configured inside of it, it is time to create tickets and examine ticket lifecycles: [LINKKK]</p>


  




  
  

