
# Ansible php7-cli/fpm role

Ansible Galaxy Playbook for php7

`php7_cli` a boolean to enable the installation of the php cli

`php7_fpm` a boolean to enable the installation of the php fpm

`php7_modules` a list of php packages to install

    php7_modules:
    - php7.0-apcu
    - php7.0-redis

`php7_fpm_conf` is a dictionary of key/value pairs for the `fpm/php-fpm.conf` global config

    php7_fpm_conf:
      emergency_restart_interval: 1m
      emergency_restart_threshold: 10
      process_control_timeout: 10s

`php7_cli_ini` and `php7_fpm_ini` are dictionaries of key/value pairs for the php.ini

    php7_fpm_ini:
      expose_php: '"Off"'
      max_execution_time: 300

`php7_fpm_pool_ini` is a dictionary of key/value pairs for the `fpm/pool.d` config

    php7_fpm_pool_ini:
      rlimit_files: 32768
      pm: static
      pm.max_children: 64

`php7_health_pool` boolean, if true, an additional pool is created for health
checks, using the socket /var/run/php{{php_version}}-fpm-health.sock, e.g.
`/var/run/php7.2-fpm-health.sock`