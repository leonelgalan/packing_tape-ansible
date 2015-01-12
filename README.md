# packing_tape-ansible\

Ansible port of [packing_tape](https://github.com/leonelgalan/packing_tape)


## Requirements

None

## Role Variables

Default variables are:

```yml
---
ruby:
  version: 2.1.5

user:
  name: deploy
  password: '' # pip install passlib && python -c "from passlib.hash import sha512_crypt; import getpass; print sha512_crypt.encrypt(getpass.getpass())" : your_password
  group: sudo
  ssh_key: ''

  postgresql:
    version: 9.3

```

Example:

```yml
- hosts: all

  roles:
    - role: ../packing_tape-ansible
    ruby:
      version: 2.1.5
    user:
      name: deploy
      password: $6$rounds=100000$nSJ9uVhbR3PzAyFk$ikgsy0FYy7g1ysSONAl4MxByy9SujhfGhYlPFf5NMcLykLXGObya.Mi29T.RCAoEwri5lwwR2uXmOdRmw7V0V.
      group: sudo
      ssh_key: ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCsNR7Iwc36JVXtNxh+CvG5oW4cFEe4PbmRJ/2XJWBxcjKZ43a9zJ2RzGGo/Uo4gk+Jr+qGPRWCjwIdVx4C+v/u7gLqsCRT/uNxmq63+AoFeKJo+YvHJ3sLxB/SkxgTgsDhEU7i9Y14CnAIzRq1GBFaJzWV+dj6tif4pDbhrsnzPYXUd/dKp7sAH/2WX50zH4qigvEl8PnqJxCc0nnnIhOqgY+T5craZRaLYAQGxVlapVCKT1YX94bL+aaWLvGTyW4JCp/jc3nN8ckY4w3Cu34mA/xP4+6N7+pKgPonzUq798ghxilDNX+s2xnUWIaJWwVNKBIqzLrhf31nPYnjGfpf leonel@smashingboxes.com
    postgresql:
      version: 9.3
```

## Dependencies

```shell
ansible-galaxy install --role-file=requirements.txt --force
```

## Vagrant

```shell
vagrant up
vagrant package
mv package.box packing_tape-vagrant-ansible.box
```

`vagrant package --output packing_tape-vagrant-ansible.box` is broken on 1.7.1, see https://github.com/mitchellh/vagrant/issues/5098.

## Packer

```zsh
berks vendor cookbooks

DIGITALOCEAN_API_TOKEN=your_digital_ocean_api_token packer build template.json
```

## Author Information

Leonel Galán (<leonel@smashingboxes.com>)
