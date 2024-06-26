# How to install SFTP 

 

We want to be able to work on files on our laptop and then copy them over to our remote VM in the cloud. To enable this functionality, we use Secure File Transport Protocol (SFTP). You will need to install an SFTP client. The SFTP client we will use is WinSCP.  

## STEPS: 

1. SSH into your VM.
2. Enable root login on you VM.
 
```bash
sudo sed -i '/PermitRootLogin/c\PermitRootLogin yes' /etc/ssh/sshd_config
```
3. Set root password to *tester*.
```bash
sudo echo -e "tester\ntester" | sudo passwd root
```
4. Restart the ssh Daemon.
```bash
sudo systemctl restart sshd
```
5. Find your public IP address
```bash
dig +short myip.opendns.com @resolver1.opendns.com
```
 

6. Click [HERE](https://atlantictu-my.sharepoint.com/:u:/g/personal/daniel_cregg_atu_ie/Ef3-CXVnbR78LjDgJAQTtlgBeWnwi4EuWv8JAeo18iLGKQ?e=gUOtB7&download=1) to download WinSCP to you PC so you can transfer files to your virtual machine.  

7. Open WinSCP. Enter YOUR Virtual Machine IP address in the Host name box. Make sure you put root in the User name box and in the Password box put tester then click login.  
![image](https://github.com/danielcregg/dc-labs/assets/22198586/3ba3fc86-e3fa-4ab0-b385-e1d317be86b4)

8. Click Yes to the following message if it pops up.  
![image](https://github.com/danielcregg/dc-labs/assets/22198586/238d66b6-8354-446e-8417-1df886d05b91)

9. Finally, you should be logged in like below. Your local windows machine files are on the left and your remote Linux VM files are on the right. Drag and drop files in either direction.   
![image](https://github.com/danielcregg/dc-labs/assets/22198586/09887dea-e316-45c1-affb-91f50c8f9f40)
