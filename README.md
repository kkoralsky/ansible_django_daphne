Daphne server for Django
========================

Daphne server for Django apps

Requirements
------------

Debian, Django app

Role Variables
--------------

- `app` - app label,
- `program_name` - supervisor label, defaults to: `{{ app }}`,
- `supervisor_conf_tpl` - path to supervisor configuration file, if unset we're using
    default defined within role: (templates/_default_supervisor.conf.j2)[https://github.com/xkoralsky/ansible_django_daphne/blob/templates/_default_supervisor.conf.j2]
- `asgi_module` - defaults to `{{ app_name }}.asgi`
- `channel_layer` - channel layer object variable name in `asgi_module`; default: `channel_layer`
- `daphne_host` - default: `127.0.0.1`
- `daphne_port` - default: `8001`
- `daphne_root_path` - root path for Daphne server; if empty, serves on every path
- `daphne_http_timeout`
- `daphne_ping_timeout`

Dependencies
------------

- `xkoralsky.django_supervisor`

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: django_daphne,   }

License
-------

BSD
