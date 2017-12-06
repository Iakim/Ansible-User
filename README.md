# Ansible for manage multiples users in linux

## Add User

### Please note the following detail:
#### Vars: add multiple variables to multiple users, the variables are the hash value of the password in /etc/shadow.
    vars:
      password_iakim: $6$JFwst493$GB.wZu0dprpNkkMxaTacI3vYIF1iiYIljYdsE.Ris5rL80y57som/lDpf5Jx.0
    - name: Create user Iakim
      user: name=iakim password={{ password_iakim }} comment="Iakim Romanov" group=wheel

## Del User

### Please note the following detail:
#### For each user a "user$" variable must be created that will have the value of the user.

     vars:
       user1: iakim
     - name: Remove User1
       user: name={{ user1 }} state=absent
     - name: Deleting the home
       shell: rm -rf /home/{{ user1 }}
