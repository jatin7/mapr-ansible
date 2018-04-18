# mapr-ansible

#### Disclaimer
Not for production use and not officially supported by MapR Technologies.
Ansible scripts work on Redhat/CentOS only.
Please note that deployment using these ansible scripts result in default passwords!

#### Pre-requisites
```
yum install -y git ansible
```

##### Clone the project
```
git clone https://github.com/mkieboom/mapr-ansible
cd mapr-ansible
```

#### Configuration
1. Specify the MapR and Eco-System versions in /group_vars/all
```
vi group_vars/all
```

2. Specify the disks for MapR-FS in /group_vars/all using a comma separated notation, eg:
disks: /dev/xvdb,/dev/xvdc,/dev/xvdd

3. Clone a template from /myhosts/ and define a cluster layout
Define the cluster layout by adding the various nodes as well as compontents to be installed.

4. Execute the ansibple playbook. For example:
ansible-playbook -i myhosts/vbox_1node_cluster cluster-unsecure.yml


#### Supported OS

* Redhat 7 or higher
* CentOS 7 or higher

Please validate the MapR OS Support Matrix prior to deployment:
http://maprdocs.mapr.com/home/InteropMatrix/r_os_matrix.html

#### Configuration options
-e "memory=low"