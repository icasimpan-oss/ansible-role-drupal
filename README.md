Ansible Role: Drupal
=========

A very basic ansible role that installs drupal8 core only (for now).

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

One drupal site per machine:

    - hosts: servers
      roles:
         - { role: icasimpan.drupal, drupal8.casimpan.com, db_user: d8_DBA, db_pass: db_PASS, db_name: d8_DB}
 
Several drupal site per machine:

    - hosts: servers
      roles:
         - { role: icasimpan.drupal, d8-dev.casimpan.com,     db_user: d8_devDBA,  db_pass: db_devPASS, db_name: d8_devDB}
         - { role: icasimpan.drupal, d8-staging.casimpan.com, db_user: d8_stgDBA,  db_pass: db_stgPASS, db_name: d8_stgDB}
         - { role: icasimpan.drupal, d8-prod.casimpan.com,    db_user: d8_prodDBA, db_pass: db_updPASS, db_name: d8_updDB}

License
-------

BSD

Author Information
------------------

Ismael Angelo A. Casimpan, Jr.
email: ismael.angelo@casimpan.com