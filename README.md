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


### Local vars

Each client configuration override global configuration.
- `mirror_cron`: (0) is added to cron. Default (true)
- `mirror_cron_day`: (O) day of the cron. Default (*)
- `mirror_cron_hour`: (O) hour of the cron. Default (23)
- `mirror_base_path`: (O) location of the files that mirror updates. Default (/mnt/repos)
- `mirror_image_path`: (0) set the path of the image
- `mirror_image`: (0) set image of web interface
- `mirror_directories_scripts`: (0) create directories to store update scripts. Default (debian,
   debian/debian, debian/debian/etc, debian/debian/bin, debian/debian-cd, debian/debian-cd/etc,
   debian/debian-cd/bin, ubuntu)
- `mirror_directories`: (0) create directories to store repositories. Default (debian, ubuntu)
- `mirror_template_debian`: (0) Copy update script debian. Default /var/lib/mirror/debian/debian/etc/ftpsync.conf
- `mirror_template_debian_cd`: (0) Copy update script debian-cd. Default /var/lib/mirror/debian/debian-cd/etc/ftpsync.conf
- `mirror_template_ubuntu`: (0) Copy update script ubuntu. Default /var/lib/mirror/ubuntu/
- `mirror_page_init`: (0) homepage destination. Default /var/www/html/mirror/index.html

### Debian repository
- `mirror_debian_rsync_host`: (0) hosts to synchronize. Default (debian.c3sl.ufpr.br)
- `mirror_debian_rsync_path`: (0) host path. Default (debian)
- `mirror_debian_rsync_user`: (0) user for private host. Default (null)
- `mirror_debian_rsync_password`: (0) password for private host. Default (null)
- `mirror_debian_cd_rsync_host`: (0) hosts to synchronize isos . Default (debian.c3sl.ufpr.br)
- `mirror_debian_cd_rsync_path`: (0) host path isos. Default (debian-cd)

## Mirror information options
- `mirror_debian_info_maintainer`: (0) email adminsys. Default (Admins <admin@admin.com>)
- `mirror_debian_info_sponsor`: (0) web sponsor. Default (<https://www.sponsor.com>)
- `mirror_debian_info_country`: (0) country. Default (Uruguay)
- `mirror_debian_info_location`: (0) city. Default (Montevideo)
- `mirror_debian_info_throughput`: (0) throughput rate. Default (10Gb)

## Include and exclude options
- `mirror_debian_arch_include`: (0) Default ()
- `mirror_debian_arch_exclude`: (0) Default ()

## Log option
- `mirror_debian_logdir`: (0) repository log path. Default ({{mirror_scripts_path}}/debian/debian/log)
- `mirror_debian_cd_logdir`: (0) iso log path Default ({{mirror_scripts_path}}/debian/debian-cd/log)

### Ubuntu repository
- `mirror_ubuntu_rsync_host`: (0) hosts to synchronize. Default (ubuntu.c3sl.ufpr.br)
- `mirror_ubuntu_rsync_path`: (0) host path. Default (ubuntu)
- `mirror_ubuntu_releases_rsync_host`: (0) hosts to synchronize isos . Default (ubuntu.c3sl.ufpr.br)
- `mirror_ubuntu_releases_rsync_path`: (0) host path releases. Default (releases)


### Other variables
- `mirror_title`: (0) your title. Default (Your title)
- `mirror_description`: (0) description. Default (Description)
- `mirror_content`: (0) content description. Default (The repositories published here are free software)
- `mirror_list`: (0) title. Default (Repository List)
- `mirror_subtitle`: (0) title. Default (Problem report)
- `mirror_foot`: (0) foot. Default (For any problem with this repository, inform admin@server.tls)
- `mirror_repository`: (0) description repositories. Default (Repositories)
- `mirror_iso_description`: (0) description isos. Default (Isos)

(O): Optional


### Quick and dirty

You should look at [defaults/main.yml](defaults/main.yml).


License
-------

GPLv3

Author Information
------------------

Original role [Víctor Torterola](https://github.com/UdelaRInterior)
