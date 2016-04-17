as root:
cd /usr/ports/ports-mgmt/portmaster
BATCH='yes' make
make install
portmaster --no-confirm -G -m 'BATCH=yes' lang/python

ansible-playbook prereq.yaml --ask-su-pass -k -i inventory.ini
ansible-playbook main.yaml --ask-su-pass -k -i inventory.ini