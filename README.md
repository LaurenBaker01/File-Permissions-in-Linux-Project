# File-Permissions-in-Linux-Project

📄 Project Description 

In this project, I’m a security professional at a large organization, who works primarily with the research team. Part of my role is to ensure users on this team are authorized with the appropriate permissions. My task is to examine the existing permissions on the file system, determine if the permissions match the authorization that should be given. If the permissions do not match, modify them to authorize the appropriate users and remove any unauthorized access.This project's main objectives is displaying permissions for files and directories and making necessary changes for the organization's safety needs.
Check file and directory details 

I have ensured that I am in the correct directory, before continuing with the pwd command. I think I should use the ls command to list the contents of the directory. The output was the projects folder, which I then used the cd command to change the working directory to the projects subdirectory. I then used the ls -la command to list all files (including hidden) and directories, including their permissions.


<img width="630" alt="port act step 3" src="https://github.com/LaurenBaker01/File-Permissions-in-Linux-Project/assets/150492784/b7632268-e18a-4172-8d83-25ec0cc5de61">

1. Describe the permissions string

The 10-character string can be deconstructed to determine who is authorized to access the
file and their specific permissions. The characters and what they represent are as follows:

● 1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s
a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.
● 2nd-4th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for the user. When one of these characters is a hyphen (-) instead, it
indicates that this permission is not granted to the user.
● 5th-7th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for the group. When one of these characters is a hyphen (-) instead, it
indicates that this permission is not granted for the group.
● 8th-10th characters: These characters indicate the read (r), write (w), and execute (x)
permissions for other. This owner type consists of all other users on the system apart
from the user and the group. When one of these characters is a hyphen (-) instead,
that indicates that this permission is not granted for other.




We will examine the permissions for project_k.txt in this example. The organization does not allow others to have writing access to any files. When we examine the permissions for project _k.txt (-rw-rw-rw-) we see that users, groups, and others all have access to reading and writing. Each triplet represents the permissions set for users, groups, and others. rw- means read and write are allowed while the dash denotes the absence of the execute permissions. 

<img width="630" alt="port act step 5 command" src="https://github.com/LaurenBaker01/File-Permissions-in-Linux-Project/assets/150492784/fdfd6e15-ad71-4716-ab1b-a8b484705040">

2. Change file permissions

   To change permissions I utilized the chmod command. The first command chmod ugo+r project_k.txt, means that users, groups, and other will be given the read permission. 
The next command chmod  o-w project_k.txt, means that others will not have permission to write. The access is denoted by the + (granted access) or the - (removing access).

<img width="630" alt="port act step 5 command" src="https://github.com/LaurenBaker01/File-Permissions-in-Linux-Project/assets/150492784/af9c40ec-eda7-48fc-9f93-68cfdc05518b">


Output:

<img width="658" alt="port act step 5 permissions post change" src="https://github.com/LaurenBaker01/File-Permissions-in-Linux-Project/assets/150492784/af26695f-172a-473e-8f57-8fd43e6381ea">

3. Change file permissions on a hidden file 
Changing a permission on a hidden file is very similar to the previous method utilized. .project_x.txt has been archived, which is why it is a hidden file. The file should not have write permissions for anyone, but the user and group should be able to read the file. Using the chmod command, we are able to change the permission. Above the permissions for .project_x.txt  read as “-rw–w—-” meaning that users have access to read and write and group has permission to write. Chmod ug+r .project_x.txt gives reading permissions to user and group. Chmod ugo-w .project_x.txt takes away writing permission from all users, group, and others. Below is the output of the commands we now see the permissions listed as “--r–r—--”, only users and group have permission to read. This is the appropriate permission because the file is archived, none should have access to make changes to the file. 

<img width="661" alt="port act step 6 perm change and results" src="https://github.com/LaurenBaker01/File-Permissions-in-Linux-Project/assets/150492784/2af7024d-2ce8-415a-bdd0-8948b414206d">

Summary

In this project, as a security professional, my role is to manage permissions for the research team at a large organization. I ensure that users have the right access to files and directories, making necessary changes for security.
I start by checking file details using commands like pwd and ls -la. For example, I examine project_k.txt and adjust permissions as needed, like granting read access with chmod ugo+r and removing others' write access with chmod o-w.
The project also covers hidden files like .project_x.txt. I modify permissions to allow only the user and group to read (chmod ug+r) and remove writing permissions for everyone (chmod ugo-w), ensuring data security.
Throughout, my focus is on aligning permissions with organizational security policies to protect sensitive information.



