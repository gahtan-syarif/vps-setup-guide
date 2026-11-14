# vps-setup-guide
first things to do when setting up a vps, listed in order:

‎1.) create the ubuntu vps (use latest available lts version) 

‎2.) access vps through web console 

3.) check if sshd is active, and if it is, immediately stop and disable it for now

‎4.) change root password to a strong one if not already

5.) set timezone and hostname if not yet set correctly

‎6.) Create a new non-root user with a strong password and give it sudo privileges (if one doesn't exist yet), then switch to it

‎7.) update the system: "sudo apt update && sudo apt upgrade -y" and then reboot if required

8.) check if system clock is synchronized properly and that automatic time synchronization is enabled

9.) change the system's default text editor to your preferred text editor

‎10.) install laptop's ssh public key to the user's authorized_keys if not yet installed (make sure the corresponding private key is password-protected) and configure sshd config to make public-key authentication mandatory as well as disabling root login

‎11.) enable sshd and make sure to test the ssh connection from a separate terminal to ensure public-key authentication is working properly and connections using unauthorized keys are being rejected

‎12.) install ufw and set it to default deny incoming and allow outgoing (make sure to still allow port 22/tcp incoming or else ssh will be locked out) and then enable it 

‎13.) install and enable fail2ban to automatically ban scanners

‎14.) install and enable unattended-upgrades for automatic security updates and schedule it to your liking (you can also optionally configure it to do automatic reboots as well as non-security updates if you dont want to do it manually)

15.) configure a swap file if running on very low-memory instance


16.) set up a vpn network between your vps and your connecting devices (easiest way is to use tailscale or wireguard)

17.) set ufw to restrict ssh access to the vpn interface/subnet so that devices outside the vpn network wouldnt be able to connect

18.) reboot the system and verify that all configured services starts and runs properly


congrats, your vps is now all set up and ready for further configuration. you can now proceed with installing and configuring whatever software and services you need for your intended use of the vps
‎