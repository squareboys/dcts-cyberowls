################################  
###Created for DCTS CyberOwls###   
################################  

# COMPLETE FORENSICS QUESTIONS FIRST  
Forensics Question 1    
Forensics Question 2  

Create users that need to be made:  
    ```sudo useradd <username>```  
Expire their password:  
    ```sudo passwd -e <username>```

  
Update all packages:  
    ```sudo apt update && sudo apt upgrade```
  
Check for unauthorized users:  
    ```sudo awk -F: '$3 >= 1000 && $1 != "nobody" {print $1}' /etc/passwd >> ~/Desktop/users.txt```  
  
Check for unauthorized sudoers:  
    ```sudo getent group sudo```  
    ```sudo getent group admin``` 
  
Remove unauthorized users:  
    ```sudo deluser <username> sudo```  
    ```sudo deluser <username> admin```    
    ```sudo deluser <username>```   
  
Enable/Install UFW:
    ```sudo apt install ufw```  
    ```sudo ufw enable```  
  
Set password age:  
    ```sudo nano /etc/login.defs```    
    **PASS_MAX_AGE: 90**  
    **PASS_MIN_AGE: 10**    
    **PASS_WARN_AGE:**  
  
Fix bad passwords:   
    ```sudo passswd <username>```   
  
Lock root:  
    ```sudo passwd -l root```  
  
Edit ssh config:    
    ```sudo nano /etc/ssh/sshd_config```  
    **PermitRootLogin no**  
    **PermitEmptyPassword no**  
  
Find media files:   
    ```find /home/ -type f -name "*.mp4"```  
    ```find /home/ -type f -name "*.mkv"```  
    ```find /home/ -type f -name "*.mp3"```  
    ```find /home/ -type f -name "*.ogg"```  
    ```find /home/ -type f -name "*.wav"```  
  
Find "hacking" tools:  
    **nmap**  
    **zenmap**  
    **ophcrack**    
    **netcat-traditional**  
    **nginx**  
    **apache2**  
    **tcpdump**  
    **nikto**  
    **wireshark**  
    ```sudo dpkg -l``` if you're having trouble finding anything

Edit sysctl:   
```sudo nano /etc/sysctl.conf```  
Disable ICMP redirects:  
    **net.ipv4.conf.all.accept_redirects = 0**  
Disable IP redirecting:  
    **net.ipv4.ip_forward = 0**  
    **net.ipv4.conf.all.send_redirects = 0**  
    **net.ipv4.conf.default.send_redirects = 0**    
Disable IP spoofing:  
    **net.ipv4.conf.all.rp_filter = 1**  
SYN Flood Protection:  
    **net.ipv4.tcp_max_syn_backlog = 2048**  
    **net.ipv4.tcp_synack_retries = 2**  
    **net.ipv4.tcp_syn_retries = 5**  
    **net.ipv4.tcp_syncookies = 1**    
Disable IPV6:  
    **net.ipv6.conf.all.disable_ipv6 = 1**  
    **net.ipv6.conf.default.disable_ipv6**  
    **net.ipv6.conf.lo.disable_ipv6**  

Enable autoupdates:  
    Update Manager -> View -> Preferences -> Automation on Mint  
    Update Manager -> Settings -> Enable autoupdates from the dropdown  
  
Install ClamAV & ClamTK:  
   ```sudo apt install clamav && sudo apt install clamtk```  
   ```freshclam```

Install fail2ban:  
   ```sudo apt install fail2ban```  
  
Find rootkits:  
   ```sudo apt install chkrootkit && sudo apt install rkhunter```  
   ```sudo chkrootkit```  
   ```sudo rkhunter --check```  
  
Disable guest in lightdm.conf:
   ```sudo nano /etc/lightdm/lightdm.conf```
   **allow-guest=false**  
   **autologin-user=none**

Secure ports:  
   ```ss -ln```
   **Check for non-loopback ports**

// I'll add more if I can think of anything.  


