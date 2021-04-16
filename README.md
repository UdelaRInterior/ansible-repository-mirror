Mirror Ansible role
============================

This role creates a public Debian and Ubuntu repository that automatically synchronizes.

Requirements
------------

Mirror-role runs on a debian distro.

Note
----

Sufficient storage space is needed according to what you want to replicate. If you leave the default variables you need approximately 3.5T

Role Variables
--------------

### Mirror basic variables

Each client configuration override global configuration.
- `mirror_group`: (O) Linux user group name. Default (repos)
- `mirror_user`: (O) Linux user. Default (repos)
- `mirror_cron`: (O) cron tasks/jobs list. Default (see [defaults/main.yml](defaults/main.yml))
  - `mirror_task`: (O) cron task/job.
  - `mirror_cron_day`: (O) cron job day.
  - `mirror_cron_hour`: (O) cron job hour.
  - `mirror_cron_minute`: (O) cron job minute.
- `mirror_base_path`: (O) path of files updated by mirror. Default (/mnt/repos)

### Mirror web site

- `mirror_apache_path`: (O) mirror Apache2 document root. Default (/var/www/html/mirror)
- `mirror_image_path`: (O) logo file path. Default ("{{ playbook_dir }}/roles/repositories/files/images/")
- `mirror_image`: (O) logo file name. Default (repos.jpg)
- `mirror_page_init`: (O) homepage file name. Default (index.html)
- `mirror_title`: (O) web title. Default (Your title)
- `mirror_description`: (O) description subtitle. Default (Description)
- `mirror_content_description`: (O) description text. Default (The repositories published here are free software)
- `mirror_list`: (O) repositories list subtitle. Default (Repository List)
- `mirror_subtitle`: (O) footer subtitile. Default (Problem report)
- `mirror_foot`: (O) footer text. Default (For any problem with this repository, inform admin@server.tls)
- `mirror_repository_description`: (O) repository prefix text. Default (Repositories)
- `mirror_iso_description`: (O) iso prefix text. Default (Isos)

### Scripts paths

- `mirror_scripts_path`: (O) scripts root path. Default (/var/lib/mirror)
- `mirror_debian_scripts_root_path`: Debian scripts root path. Default "{{ mirror_scripts_path }}/debian"
- `mirror_debian_scripts_path`: (O) Debian repository scripts path. Default "{{ mirror_debian_scripts_root_path }}/debian"
- `mirror_debian_cd_scripts_path`: (O) Debian isos scripts path. Default "{{ mirror_debian_scripts_root_path }}/debian-cd"
- `mirror_ubuntu_scripts_path`: (O) Ubuntu scripts path. Default "{{ mirror_scripts_path }}/ubuntu"

### Debian repository
- `mirror_debian_rsync_host`: (O) Debian rsync server. Default (debian.c3sl.ufpr.br)
- `mirror_debian_rsync_path`: (O) server path. Default (debian)
- `mirror_debian_rsync_user`: (O) server user name (private host). Default (null)
- `mirror_debian_rsync_password`: (O) user password (private host). Default (null)
- `mirror_debian_cd_rsync_host`: (O) Debian isos rsync server. Default (debian.c3sl.ufpr.br)
- `mirror_debian_cd_rsync_path`: (O) server isos path. Default (debian-cd)

#### Mirror service owner details
- `mirror_debian_info_maintainer`: (O) maintainer email. Default (Admins <admin@admin.com>)
- `mirror_debian_info_sponsor`: (O) sponsor web. Default (<https://www.sponsor.com>)
- `mirror_debian_info_country`: (O) country. Default (Uruguay)
- `mirror_debian_info_location`: (O) city. Default (Montevideo)
- `mirror_debian_info_throughput`: (O) throughput rate. Default (10Gb)

#### Include and exclude options
- `mirror_debian_arch_include`: (O) Default ()
- `mirror_debian_arch_exclude`: (O) Default ()
- `mirror_debian_cd_arch_include` : (O) Default ()
- `mirror_debian_cd_arch_exclude` : (O) Default ()

#### Log options
- `mirror_debian_logdir`: (O) Debian repository log path. Default ({{mirror_scripts_path}}/debian/debian/log)
- `mirror_debian_cd_logdir`: (O) Debian isos log path. Default ({{mirror_scripts_path}}/debian/debian-cd/log)

### Ubuntu repository
- `mirror_ubuntu_rsync_host`: (O) Ubuntu rsync server. Default (ubuntu.c3sl.ufpr.br)
- `mirror_ubuntu_rsync_path`: (O) server path. Default (ubuntu)
- `mirror_ubuntu_releases_rsync_host`: (O) Ubuntu isos rsync server . Default (ubuntu.c3sl.ufpr.br)
- `mirror_ubuntu_releases_rsync_path`: (O) server isos path. Default (releases)

### Other variables
- `mirror_telegram_token`: (O) Telegram token for update errors communications. Default (null)
- `mirror_telegram_chat_id`: (O) Telegram chat ID. Default (null)

(O): Optional


Quick and dirty
---------------

You should look at [defaults/main.yml](defaults/main.yml).


License
-------

GPLv3

Author Information
------------------

Original role [Víctor Torterola](https://github.com/UdelaRInterior)
