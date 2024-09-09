# ansible

# password-less authentication using pem key
ssh-copy-id -f "-o IdentityFile <key path>" username@public-ip
ssh-copy-id -f "-o IdentityFile ~/Downloads/ansible-key.pem" ubuntu@15.206.205.83


ansible -i inventroy.ini -m ping all

ansible -i inventroy.ini -m ping test

# sample ad hoc command for directory creation
ansible -i inventroy.ini -m file -a "path=/home/ubuntu/<file or directory name> state=directory"

# sample ad hoc command for file creation
ansible -i inventroy.ini -m file -a "path=/home/ubuntu/<file or directory name> state=touch"

# ansible playbook execute command
ansible-playbook -i inventroy.ini sample-playbook.yml

# create an ansible role
ansible-galaxy role init <role name>