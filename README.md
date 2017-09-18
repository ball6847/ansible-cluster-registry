## Usage

```sh
# before starting, you should activate virtualenv or direnv if you have one.
# assuming you are using direnv (which I personally recommend it)
# this activate python environment
direnv allow

# install ansible, you can skip this if you prefer the global ansible bin of your system
pip install -r requirements.txt

# get all roles from ansible gallaxy
ansible-gallaxy install -r roles/requirements.yml

# ---------------
# now get your hand dirty by creating some playbooks
# ---------------

# ... and when you are ready

# bring virtual machine up for testing
vagrant up

# start your play
ansible-playbook main.yml
```

On the the first run you might need to run with this command to force apt-select.

```
ansible-playbook main.yml -e apt_select_ignore_period=0
```
