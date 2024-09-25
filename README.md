# ubuntu-dod-stig-compliance
1. Clone the repo localy: 
`git clone https://github.com/alxlcr/ubuntu-dod-stig-compliance.git cloud-init`
2. Change the ubuntu_admin password:
`mkpasswd -m sha-512 "S3cr3tPassword!"`
3. Build the ISO with:
`mkisofs -V cidata -lJR -o cloud-init.iso user-data meta-data`
4. Start a brand new VM using both the 2404 server ISO and the cloud-init.iso. Type yes and the autoinstall prompt and observe the output.
This was tested in Proxmox.
