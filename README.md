<h1>File permissions in Linux</h1>
<h2>Project description</h2>
The company’s Research team is in need to update the file permissions to specific files and sub-directories within the projects directory. The current permissions do not follow the Principle of Least Privilege. Updating the permissions to these files and directories will keep the system secure. To complete this project, I used Linux commands and performed the tasks below.

<h3>Languages and Utilities Used</h3>
- Linux Commands

<h3>Environments Used </h3>
- Linux on Google's Qwiklabs platform </br>

<h2>Check file and directory details.</h2>
The below Linux code shows the current permissions to the files and directories (including hidden files and directories) inside the Projects directory:

<img src="https://i.imgur.com/gCADgW6.png" height="80%" width="80%" alt="File and Directory permissions initially"/>

The Linux command <b>ls</b> is used to display the contents of the Projects directory. The options <b>-l</b> is used to display the permissions of the listed items, and the options <b>-a</b> is used to display any hidden files and directories. Combining <b>-l</b> and <b>-a</b> to <b>-la</b> will display the permission of all files and directories including the hidden ones. The 10-character string in the first column represents the permissions set on each file or directory.
<h2>The permissions strings explained</h2>
The 10-character string define the permission of the file. The characters and what they represent are as follows:
<ul> <li>1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.</li>
<li>2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.</li>
<li>5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.</li>
<li>8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.</li></ul>
<h2>Changing file permissions</h2>
The team decided that other users should not have write access to their files. By listing the file permissions, I determined that <b>project_k.txt</b> has write permissions for other users.
To remove the write permissions, I used the following Linux commands:

<img src="https://i.imgur.com/SoyjTzr.png" height="80%" width="80%" alt="Changing file permission"/>

I used the <b>chmod</b> command, with the attributes <b>o-w project_k.txt</b>, which means to remove write access to other users to the file <b>project_k.txt</b>. The updated file permissions are displayed using the commands <b>ls -la</b>.
<h2>Change file permissions on a hidden file</h2>
The team decided that the Archived file <b>project_x.txt</b> should only have read access only to the user and the group, and nobody should have write access to the file.

This was achieved using the following Linux commands:

<img src="https://i.imgur.com/rlYLZxC.png" height="80%" width="80%" alt="Changing file permission to a hidden file"/>

Since the user and the group had write permission, it had to removed and the read permission is to be granted to the group users. The command used is <b>chmod</b> with the attributes <b>u-w, g-w, g+r</b> to the file <b>.project_x.txt</b>. Since the other users did not have any permissions, there were no changes to the other users permissions.
The updated permissions are listed using the <b>ls -la</b> command.
<h2>Change directory permissions</h2>
The company wanted only <b>researcher2</b> to have access permission to the directory drafts. This means that only the user researcher2 should have execute permissions.

This was achieved using the follow Linux commands:

<img src="https://i.imgur.com/oG90OpV.png" height="80%" width="80%" alt="Changing directory permission"/>

Again, the <b>chmod</b> command was used with the attributes <b>g-x drafts</b> which would mean that the execute access will be removed for the group users to the drafts directory.
The updated permissions are listed using the <b>la -la</b> command.
<h2>Summary</h2>
The read, write and execute permissions to multiple files and directories were changed as per the company and team’s directions. The commands used were <b>la -la</b> to list all file and directory permissions including hidden files and directories. The command <b>chmod</b> was then used to update the file and directory permissions as per the instructions provided.




