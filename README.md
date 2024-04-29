# Vagrant manual

`VAGRANT_EXPERIMENTAL="disks" vagrant up`

`ansible-galaxy collection install community.general`

`ansible-galaxy collection install ansible.posix`

# ansible-bdp

```
ansible-playbook -i inventories/vagrant.yaml zk.yml -b --private-key vagrant -u vagrant
ansible-playbook -i inventories/vagrant.yaml spark.yml -b --private-key vagrant -u vagrant
ansible-playbook -i inventories/vagrant.yaml spark.yml -b --private-key vagrant -u vagrant --tags spark::masters-start
ansible-playbook -i inventories/vagrant.yaml spark.yml -b --private-key vagrant -u vagrant --tags spark::workers-start
```