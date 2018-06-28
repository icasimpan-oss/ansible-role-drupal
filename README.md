Ansible Role: Drupal
=========

A very basic ansible role that installs either drupal8 core(default) or drupal7 core latest version.

Requirements
------------

There are no explicit requirements here yet. But ideally, you should already have installed the following (either manually or via another ansible role):
* composer
* drush
* php
* mysql

Role Variables
--------------

Consult ```defaults/main.yml``` for anything that you can override.


Dependencies
------------

Not yet explicitly listed but please refer to Requirements above for details.

Example Playbook
----------------
Default Drupal Admin credentials:
* username: admin
* password: drupal

One drupal site per machine:

    - hosts: servers
      roles:
         - { role: icasimpan.drupal, site_domain: drupal8.casimpan.com, db_user: d8_DBA, db_pass: db_PASS, db_name: d8_DB}
 
Several drupal site per machine:

    - hosts: servers
      roles:
         - { role: icasimpan.drupal, site_domain: d8-dev.casimpan.com,     db_user: d8_devDBA,  db_pass: db_devPASS,  db_name: d8_devDB}
         - { role: icasimpan.drupal, site_domain: d8-staging.casimpan.com, db_user: d8_stgDBA,  db_pass: db_stgPASS,  db_name: d8_stgDB}
         - { role: icasimpan.drupal, site_domain: d8-prod.casimpan.com,    db_user: d8_prodDBA, db_pass: db_prodPASS, db_name: d8_prodDB}

Mixed drupal7 and drupal8 sites per machine:

    - hosts: servers
      roles:
         - { role: icasimpan.drupal, drupal_ver: 7x, site_domain: d7-www.casimpan.com, db_user: d7_DBA,  db_pass: db_d7PASS,  db_name: d8_d7DB}
         - { role: icasimpan.drupal,                 site_domain: d8-www.casimpan.com, db_user: d8_DBA,  db_pass: db_d8PASS,  db_name: d8_d8DB}

License
-------

BSD

Author Information
------------------

* Ismael Angelo A. Casimpan, Jr.
* email: ismael.angelo@casimpan.com
