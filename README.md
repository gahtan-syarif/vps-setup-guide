# vps-setup-guide
first things to do when setting up a vps

‎1) create the ubuntu vps (use latest available lts version) 

‎2) access vps through web console 

3.) set timezone and hostname if not yet set correct

‎4) change root password to a strong one if not already

‎5) Create a new user with a strong password and give it sudo privileges (if one doesn't exist yet) 

‎6) update the system: sudo apt update && sudo apt upgrade 

‎7) install basic utils: ufw, fail2ban, unattended-upgrades, micro, curl, wget, openssh-server (if not yet installed)

‎8) Reboot if a kernel update requires it and reconnect through the web console 

‎9) install laptop's ssh public key to the user's authorized_keys if not yet installed and configure sshd config to accept public key auth 

‎10) Make sure to test the ssh connection from a separate terminal and check if public key auth is working properly 

‎11) configure sshd config to disable password authentication and root login and then reload sshd 

‎12) set ufw to default deny incoming and allow outgoing (make sure to still allow port 22 incoming or else ssh will be locked out) and then enable it 

‎13) enable fail2ban 

‎14) enable unattended upgrades if not yet enabled
 
‎15) (optional) set up a wireguard vpn network between your vps and your connecting devices and then set ufw to restrict ssh access to the wireguard interface/subnet 
‎
‎