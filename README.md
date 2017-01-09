# Ansible role for ruby of user

- Setup ruby from git into home directory

## Requirements

- Debian
- Ubuntu

## Role Variables

- `git_update`: `update` option of [git module](http://docs.ansible.com/git_module.html)
- `git_depth`: `depth` option of [git module](http://docs.ansible.com/git_module.html)
- `ruby_git_user`: user
- `ruby_git_group`: group
- `ruby_git_src_dir`: git clone directory
- `ruby_git_prefix`: `--prefix` argument of configure
- `ruby_git_openssl_dir`: `--with-openssl-dir` argument of configure
- `ruby_git_cppflags`: cppflags argument of configure
- `ruby_git_rbenv_root`: rbenv root

## Dependencies

- [znz.user-libressl](https://github.com/znz/ansible-role-user-libressl) role or set `ruby_git_openssl_dir`
- rbenv installed to `ruby_git_rbenv_root`

## Example Playbook

Normal usage:

    ---
    - hosts: all
      become: no
      roles:
      - znz.user-ruby-git

## Example requirements.yml

    - src: https://github.com/znz/ansible-role-user-ruby-git
      version: master
      name: znz.user-ruby-git

## License

MIT License
