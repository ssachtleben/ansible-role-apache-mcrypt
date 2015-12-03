# Ansible Role Apache Mcyrpt

## Why this role?
On Ubuntu its not enough to install the mcrypt module for apache. It also needs activated. So if you use: 
https://github.com/geerlingguy/ansible-role-php/ with this configuration:

```
  - role: geerlingguy.php
    php_packages:
      - php5
      - php5-common
      - php5-mcrypt
      - php5-curl
      - php5-gd
```

Applications on Ubuntu which using mcrypt will crash with the following error message since mcrypt needs to be activated:

`PHP Fatal error: Call to undefined function mcrypt_module_open()`

## How to use
* Add this role via `ansible-galaxy install ssachtleben.apache-mcrypt`
* Configure it in your role

## Example configuration
Here is a working example configuration after adding the role:

```
  - role: geerlingguy.php
    php_packages:
      - php5
      - php5-common
      - php5-mcrypt
      - php5-curl
      - php5-gd

  - role: ssachtleben.apache-mcrypt
```