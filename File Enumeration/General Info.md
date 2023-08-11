`ls` to list files
`-a` to show hidden files
`-l` to show more info
Combine together into `ls -la`

![[Pasted image 20221208160236.png]]

**1st column**
The first letter is if the content is directory, file or link. If it is d, it’s a directory, if it’s - (minus sign) it means that the content is file. While if it is an l (small L character), means the content is a link
The next 9 are the file permissions. The first 3 **rwx** characters are for **Owner** of the file, the second 3 characters are for **Group owner** of the file and the last 3 characters are for **public** access to the file.

**2nd column**
How many links to this file

**3rd column**
This tells us about who is the owner of the file/directory

**4th column**
This tells us about who the group owner of the file/directory

**5th column**
This tells us about the size of the file/directory in bytes unit. Except for directories, the size will always count as 4096 bytes

**6th column**
This tells us about the last time and date the file is modified

**7th column**
This tells us the filename or directory name
