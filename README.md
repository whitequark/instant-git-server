# instant git server

to set up a git server frontend at `githosting.org`:

  1. obtain a debian 8 machine and point `githosting.org` at it
  2. `ssh-keygen -f id_rsa`
  3. `ssh-copy-id -i id_rsa.pub root@githosting.org`
  4. install ansible >=2.2 locally
  5. fill in placeholders in `hosts.cfg.example` and save as `hosts.cfg`
  6. `ansible-playbook playbook.yml`
  7. `export GIT_SSH_COMMAND="ssh -i $(pwd)/id_rsa"`
  8. `git clone git@githosting.org:gitolite-admin`
  9. [add some repositories](http://gitolite.com/gitolite/basic-admin/)
  10. done

skip all steps with `id_rsa` in them if you would rather just use your
global SSH key for administration.
