apt install snapd
systemctl enable --now snapd.socket

ln -s /var/lib/snapd/snap /snap
ls /
ls -alh /

snap install microk8s --classic

// if error, you can reinstall and install again snapd


# on centos
firewal-cmd --list-all
firewal-cmd --zone=public --permanent --add-port 25000/tcp
# on ubuntu
sudo ufw status verbose
sudo ufw allow 25000/tcp

// please you ca'nt turn off firewall, its a bad idea


microk8s status

//if permision 
sudo usermod -a -G microk8s ubuntu
newgrp microk8s
mkdir ~/.kube
sudo chown -R ubuntu ~/.kube
//and cek again

//if not found
ls /snap/bin
PATH=$PATH:/snap/bin
//and cek again



# on master
microk8s add-node
// add echo "192.168.x.x worker1" | sudo tee -a /etc/hosts on the master

//copy to following source
# on node 1
microk8s join {copying on master source}



#######################################

# starting on master | controller

microk8s enable dashboard dns helm3 metallb prometheus rbac