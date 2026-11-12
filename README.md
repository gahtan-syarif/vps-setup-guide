# vps-setup-guide
first things to do when setting up a vps

‎1.) create the ubuntu vps (use latest available lts version) 

‎2.) access vps through web console 

‎3.) change root password to a strong one if not already

4.) set timezone and hostname if not yet set correctly

‎5.) Create a new non-root user with a strong password and give it sudo privileges (if one doesn't exist yet), then switch to it

‎6.) update the system: "sudo apt update && sudo apt upgrade -y" and then reboot if required

‎7.) install laptop's ssh public key to the user's authorized_keys if not yet installed and configure sshd config to accept public key auth 

‎8.) enable sshd and make sure to test the ssh connection from a separate terminal and check if public key auth is working properly 

‎9.) configure sshd config to disable password authentication and root login and then reload sshd 

‎10.) install ufw and set it to default deny incoming and allow outgoing (make sure to still allow port 22 incoming or else ssh will be locked out) and then enable it 

‎11.) install and enable fail2ban 

‎12.) install and enable unattended-upgrades
 
‎13.) (optional) set up a wireguard (or other) vpn network between your vps and your connecting devices and then set ufw to restrict ssh access to the wireguard interface/subnet 

14.) (optional) configure a swap file if running on very low-memory instance
‎
‎