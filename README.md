Config corebaba, cucm and edge using BASIC-CONFIG
Copy paste lang 
For Corebaba:
112-147
151-154

For CUCM:
173-192
195-198

For EDGE 
217-244
248-251

NOTE always choose 2048 size for RSA 

Next Open VMWare Rocky Linux
use ip addr to check ip
check the ip address of the linux ex 208.8.8.128
!!! Make sure naka NAT 

Open Securecrt
Quick Connect 
SSH2 > IP ADDRESS NI ROCKY LINUX
login mo root at pass mo

git clone tas yung na edit mo na github

then punta sa ansible 
cd /etc/ansible
nano hosts 
palitan yung corebaba ng name na switch
save

then pag tapos ssh admin@devices
devices:
corebaba - 10.M.1.4
cucm - 10.M.100.8
edge - 10.M.M.1

pag di gumana paste mo remove ssh sa LINUX
ssh-keygen -f "/root/.ssh/known_hosts" -R "10.M.1.4"
ssh-keygen -f "/root/.ssh/known_hosts" -R "10.M.100.8"
ssh-keygen -f "/root/.ssh/known_hosts" -R "10.M.M.1"

after that move ka linux sa github clone mo 
cd automation
ls
pag ls mo dapat makita mo mga laman ng github mo
then 
ansible-playbook run_all.yaml

