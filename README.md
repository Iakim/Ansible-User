# Ansible for add multiples users in linux

### Please note the following detail:
#### Vars: add multiple variables to multiple users, the variables are the hash value of the password in /etc/shadow
    vars:
      password_iakim: $6$JFwst493$GB.wZu0dprpNkkMxaTacI3vYIF1iiYIljYdsE.Ris5rL80y57som/lDpf5Jx.0
    - name: Create user Iakim
      user: name=iakim password={{ password_iakim }} comment="Iakim Romanov" group=wheel
