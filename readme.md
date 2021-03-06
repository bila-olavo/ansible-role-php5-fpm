
# Ansible php5-cli/fpm role

Ansible Galaxy Playbook for php5

`php5_cli` a boolean to enable the installation of the php cli

`php5_fpm` a boolean to enable the installation of the php fpm

`php5_modules` a list of php packages to install

    php5_modules:
    - php-apcu
    - php-pear
    - php5.6-mysql
    - php5.6-mbstring
    - php5.6-soap
    - php5.6-curl
    - php5.6-gd
    - php5.6-gmp
    - php5.6-intl
    - php5.6-json
    - php5.6-mcrypt
    - php5.6-mysql
    - php5.6-readline
    - php5.6-dev
    - php5.6-xml

`php5_fpm_conf` is a dictionary of key/value pairs for the `fpm/php-fpm.conf` global config

    php5_fpm_conf:
      emergency_restart_interval: 1m
      emergency_restart_threshold: 10
      process_control_timeout: 10s

`php5_cli_ini` and `php5_fpm_ini` are dictionaries of key/value pairs for the php.ini

    php5_fpm_ini:
      expose_php: '"Off"'
      max_execution_time: 300

`php5_fpm_pool_ini` is a dictionary of key/value pairs for the `fpm/pool.d` config

    php5_fpm_pool_ini:
      rlimit_files: 32768
      pm: static
      pm.max_children: 64

`php5_health_pool` boolean, if true, an additional pool is created for health
checks, using the socket /var/run/php{{php_version}}-fpm-health.sock, e.g.
`/var/run/php/php5.6-fpm.sock`