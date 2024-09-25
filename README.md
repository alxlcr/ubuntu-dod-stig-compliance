# ubuntu-dod-stig-compliance
This is the user-data file needed to build a minimal Ubuntu 2404 server hardened with the Ubuntu 2004 stig [^1]
1. Clone the repo localy: 
`git clone https://github.com/alxlcr/ubuntu-dod-stig-compliance.git cloud-init`
2. Change the ubuntu_admin password:
`mkpasswd -m sha-512 "S3cr3tPassword!"`
3. Build the ISO with:
`mkisofs -V cidata -lJR -o cloud-init.iso user-data meta-data`
4. Start a brand new VM using both the 2404 server ISO and the cloud-init.iso. Type yes at the autoinstall prompt and observe the output.
5. Once completed ssh (on port 50022) into the new server and run:

`cd /stig`
`sudo ./enforce.sh`
observe the output and restart when completed:
`sudo reboot`
6. You now have minimal Ubuntu 2404 Server, with Ansible, Docker and some basic packages ready for use.

[^1]: Hardening is based on the official 2004 automation package from here: https://dl.dod.cyber.mil/wp-content/uploads/stigs/zip/U_CAN_Ubuntu_20-04_LTS_V1R11_STIG_Ansible.zip
[^2]: This was tested in Proxmox
