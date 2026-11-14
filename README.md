# vps-setup-guide
first things to do when setting up a vps, listed in order:

‎1.) create the ubuntu vps (use latest available lts version) 

‎2.) access vps through web console 

‎3.) change root password to a strong one if not already

4.) set timezone and hostname if not yet set correctly

‎5.) Create a new non-root user with a strong password and give it sudo privileges (if one doesn't exist yet), then switch to it

‎6.) update the system: "sudo apt update && sudo apt upgrade -y" and then reboot if required

7.) check if system clock is synchronized properly and that automatic time synchronization is enabled

8.) change the system's default text editor to your preferred text editor

‎9.) install laptop's ssh public key to the user's authorized_keys if not yet installed (make sure the corresponding private key is password-protected) and configure sshd config to make public-key authentication mandatory as well as disabling root login

‎10.) enable sshd (or reload if already active and enabled) and make sure to test the ssh connection from a separate terminal to ensure public-key authentication is working properly and connections using unauthorized keys are being rejected

‎11.) install ufw and set it to default deny incoming and allow outgoing (make sure to still allow port 22/tcp incoming or else ssh will be locked out) and then enable it 

‎12.) install and enable fail2ban to automatically ban scanners

‎13.) install and enable unattended-upgrades to enable automatic security updates and schedule it to your liking (you can also optionally configure it to do automatic reboots as well as non-security updates if you dont want to do it manually)

14.) configure a swap file if running on very low-memory instance


15.) (optional, strongly recommended) set up a wireguard (or other) vpn network between your vps and your connecting devices and then set ufw to restrict ssh access to the vpn interface/subnet 

16.) reboot the system and verify that all configured services starts and runs properly


congrats, your vps is now all set up and ready for further configuration. you can now proceed with installing and configuring whatever software and services you need for your intended use of the vps
‎