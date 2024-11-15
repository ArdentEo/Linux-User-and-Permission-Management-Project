<h1>Linux User Access Management Lab</h1>


<h2>Description</h2>
This is a lab I did from the Google Cybersecurity Certification that concentrates on managing user authentication and authorization in a Linux environment, I utilized Bash shell commands to achieve this. The lab encompassed administering user and group accounts, handling file ownership and permissions, and implementing security best practices. By ensuring proper access controls, I can enhance the system's security posture and gained proficiency in command-line tools and scripting.
<br />


<h2>Steps</h2>

1. Implemented user authentication mechanisms by adding new users **`(useradd)`** to a Linux system, simulating the onboarding process in an organizational environment.

2. Configured primary and secondary group memberships using **`usermod -g`** and **`usermod -aG`**, allowing for structured access control and facilitating inter-departmental collaboration between Research and Sales teams.

3. Managed file ownership and permissions with **`chown`**, assigning project files to appropriate users to maintain accountability and data integrity.

4. Executed user deprovisioning procedures using **`userdel`** and **`groupdel`** to securely remove users and their associated groups which emulates a user's departure, ensuring no residual access remained.

5. In this project I aimed to better my knowledge of Linux security practices, reinforcing the importance of proper user management in preventing unauthorized access.

<h2>Technical Skills </h2>

1. Operating Systems: Linux

2. System Administration: User and group management, file permissions, and ownership

3. Security Practices: Authentication and authorization management

4. Command-Line Tools: useradd, usermod, userdel, chown, groupdel

5. Scripting: Bash shell proficiency

<h2>Program walk-through:</h2>

<p>In this example, a new employee with the username <code>researcher9</code> joins our organization. My tasks are as follows:</p>

<ol>
    <li><strong>Add</strong> the new user to the system and assign them to their primary group.</li>
    <li><strong>Assign</strong> file ownership to the new user for a specific project.</li>
    <li><strong>Add</strong> the user to a supplementary group as their role expands.</li>
    <li><strong>Delete</strong> the user from the system when they leave the organization.</li>
</ol>

<hr>

<h3> 1: Add a New User and Assign a Primary Group</h3>

<p><strong>Objective:</strong> Add <code>researcher9</code> to the system and set <code>research_team</code> as their primary group.</p>

<p><strong>Steps:</strong></p>

<ol>
    <li>
        <strong>Add the new user to the system:</strong>
        <p>I use the <code>useradd</code> command to create the new user:</p>
    
  <img src="https://i.imgur.com/ca8ifQZ.png" height="80%" width="80%" alt=""/>
    <li>
        <strong>Assign <code>research_team</code> as the primary group:</strong>
        <p>Next, I assign the primary group using the <code>usermod</code> command:</p>
         <img src="https://i.imgur.com/HrCpkmD.png" height="80%" width="80%" alt=""/>
        
        
  <p>Alternatively, I could have combined these steps when creating the user:</p>
   <img src="https://i.imgur.com/VN4SnL7.png" height="80%" width="80%" alt=""/>
        
</ol>

<p><strong>Outcome:</strong> The user <code>researcher9</code> is now added to the system with <code>research_team</code> as their primary group.</p>


<hr>

<h3>Task 2: Assign File Ownership</h3>

<p><strong>Objective:</strong> Make <code>researcher9</code> the owner of the <code>project_r.txt</code> file.</p>

<p><strong>Step:</strong></p>

<ul>
    <li>
        <strong>Change the file owner to <code>researcher9</code>:</strong>
        <p>I use the <code>chown</code> command to transfer ownership:</p>
      <img src="https://i.imgur.com/myASZ0a.png" height="80%" width="80%" alt=""/>
    </li>
</ul>

<p><strong>Outcome:</strong> <code>researcher9</code> now owns the <code>project_r.txt</code> file and has full control over it.</p>


<hr>

<h3>Task 3: Add the User to a Secondary Group</h3>

<p><strong>Objective:</strong> Add <code>researcher9</code> to the <code>sales_team</code> group as a secondary group while keeping <code>research_team</code> as their primary group.</p>

<p><strong>Step:</strong></p>

<ul>
    <li>
        <strong>Add to the secondary group:</strong>
        <p>I use the <code>usermod</code> command with the <code>-a</code> (append) and <code>-G</code> (groups) options:</p>
       <img src="https://i.imgur.com/IPLAN4l.png" height="80%" width="80%" alt=""/>
    
</ul>

<p><strong>Outcome:</strong> <code>researcher9</code> is now a member of both the <code>research_team</code> (primary group) and <code>sales_team</code> (secondary group).</p>



<hr>

<h3>Task 4: Delete the User and Clean Up</h3>

<p><strong>Objective:</strong> Remove <code>researcher9</code> from the system and delete any residual groups when they leave the company.</p>

<p><strong>Steps:</strong></p>

<ol>
    <li>
        <strong>Delete the user account:</strong>
        <p>I run the <code>userdel</code> command:</p>
        <img src="https://i.imgur.com/UHN4qs2.png" height="80%" width="80%" alt=""/>
        <p> This command might output:</p>
        <pre><code>userdel: group researcher9 not removed because it is not the primary group of another user.</code></pre>
    </li>
    <li>
        <strong>Remove the user's group:</strong>
        <p>To alleviate the issue, I can delete the group associated with the user:</p>
        <img src="https://i.imgur.com/DDtMiUv.png" height="80%" width="80%" alt=""/>
    </li>
</ol>

<p><strong>Outcome:</strong> <code>researcher9</code> is completely removed from the system, and any associated groups are deleted to maintain system cleanliness.</p>

<p>In this lab I demonstrated the common commands used to manage a user account during its lifecycle.</p>





