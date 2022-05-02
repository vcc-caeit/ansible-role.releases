Ansible Role: releases
======================

This role helps with configuring base content for a releases mirror, as well as pre-staging releases into the staging area `.pool` and then actually making the release happen.
The pre-staging are only ran when specifing the tag `prepare` and the release only happens when specifying the `release` tag.

Role Variables
--------------

The path on the remote you would like to populate with your releases.

    releases_path: /var/www

Which path on your controller to look for file and template content in. Could be a relative to `files`, `inventory_dir` or `playbook_dir` and defaults to `None`.
Defaults in the playbook uses the deprecated `releases_base`.

    releases_files: none
    releases_templates: none

File pattern for your release files. The default is `custom.*` since that is the default for what the `vcc-caeit.build_iso` role produce.

    releases_pattern: custom.*

List of files to keep as visible release symlinks. This could be used if you have valid release files that doesn't match `releases_pattern`.

    releases_keepfiles: []

Ownership of files and directories can be set.

    releases_owner: www-data
    releases_group: www-data

Example Playbook
----------------

    - hosts: mirrors
      roles:
        - vcc_caeit.releases

License
-------

GPLv2

Author Information
------------------

This role was created in 2018 by Nafallo Bjälevik, whilst doing consultancy work for [Volvo Cars Corporation](http://www.volvocars.com/).
