<img src="https://i.imgur.com/tcuJTwO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h1>File Shares and Permissions (Extension of Active Directory Lab)</h1>
This tutorial explores how to grant file permissions and share files with different users utilizing active directory.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Windows Explorer

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)


<h2>Steps</h2>

<p>
</p>
<p>

Let's start off by logging in as our domain account (if you remember from previous labs, this will be mydomain.com\jane_admin) into DC-1. Then go to Client-1 and login as a user that you created with the powershell scripts in the active directory lab (mydomain.com\<someuser>). After this, go back onto DC-1 and create 4 new folders on the C:\ drive, "read-access", "write-access", "no-access", and "accounting". Then set the following permissions for the domain users. For "read-access" set it to "read-only" for users. For "write-access" set it to "read and write only" for users. For "no-access" set it to "read and write only" for Domain Admins. For now, leave the accounting folder alone.

<img src="https://i.imgur.com/qoocVtE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0xQzvFb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/pBnGdMK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Nzmd7zd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/vCeXcPG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/sJKPGpy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>

Now, go back to client-1 and navigate the shared folder, (start, run \\dc-1) and try and access the folders that you've created. Go and observe which folders you can and can't access.

<img src="https://i.imgur.com/CPy3ZgQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/o0CsWnM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>

Finally, let's explore the accountants folder that we created. Go back to DC-1, and in Active Directory, create a security group called "ACCOUNTANTS". After, in the folder that you created earlier, set the following permissions: Folder: "Accounting", Group: "ACCOUNTANTS", Permissions: "Read and Write Only", then go back to Client-1 and try and access the accountants folder as a random user that you created, you should notice that it doesn't work. After, log-out of client-1 as that user, and go back to DC-1 and make that user a member of the "ACCOUNTANTS" security group, then go back and login to Client-1 as that user and try to access the accounting folder, does it work now?

<img src="https://i.imgur.com/MJLiqdK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/nKdrnGZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/PtsWrv2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/merT75L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jUJzYky.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
