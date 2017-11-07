## Vagzooible
* For running full process
    $ vagrant up

* For running just tests
    $ ansible-playbook -e 'host_key_checking=False' -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory provisioning/tasks/main.yml --tags tests