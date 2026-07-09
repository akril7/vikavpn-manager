Hardening new empty server

--------------------------------------------------------------------------
Vars:

bootstrap_secret:
  root_password_hash
  ssh_user_password_hash 

bootstrap:
  ssh:
    user - username for new user
    port - new port for ssh server
    authorized_keys - list of keys for root
