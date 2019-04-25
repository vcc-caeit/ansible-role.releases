Ansible Role: releases
=========

This role helps with configuring base content for a releases mirror, as well as pre-staging releases into the staging area `.pool` and then actually making the release happen.
The pre-staging are only ran when specifing the tag `prepare` and the release only happens when specifying the `release` tag.

Role Variables
--------------

The path on the remote you would like to populate with your releases.

    releases_path: /var/www

Which path on your controller to look for base content in. Could be a relative to `files`, `inventory_dir` or `playbook_dir`.

    releases_base: releases/

File pattern for your release files. The default is `custom.*` since that is the default for what the `vcc-caeit.build_iso` role produce.

    releases_pattern: custom.*

Example Playbook
----------------

    - hosts: mirrors
      roles:
        - vcc-caeit.releases

License
-------

GPLv2

Author Information
------------------

This role was created in 2018 by Nafallo Bjälevik, whilst doing consultancy work for [Volvo Cars Corporation](http://www.volvocars.com/).
