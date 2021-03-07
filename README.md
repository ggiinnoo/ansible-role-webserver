Setup webserver (nginx | httpd)
=========

![ggiinnoo.webserver](https://github.com/ggiinnoo/ansible-role-webserver/workflows/Ansible%20role%20webserver/badge.svg)

This playbook allows you to configure and httpd or nginx web server.
If you require some vhost's take a look at my other ansible role's.

This playbook checks if you have nginx or httpd installed already. if you select nginx and httpd is already installed it will stop and do nothing.

TODO
----
-

Requirements
------------

There are no requirements as of yet


Role Variables
--------------

While everyting will work out of the box without any changes, there are a couple variables that you can change. (the vallues that are set bellow are the standard ones)
The most important will be the:

	webService: httpd
You can set this to either httpd or nginx. The standard vallue will be httpd

The port's can also be set here:

	webServicePort: 80
	webServiceSecurePort: 443

If you want to disable server signatures:

	webServiceSignatures: true

The following variables can be set but will be most of the time not needed

	apacheErrorLog: logs/error_log
	apacheAccessLog: logs/access_log

	apacheSecureErrorLog: logs/ssl_error_log
	apacheSecureAccessLog: logs/ssl_access_log

	apacheLogLevel: warn
	apacheUser: apache
	apacheGroup: apache
	apacheAdmin: root@localhost

	apacheConfLocationSSL: "/etc/httpd/conf.d/ssl.conf"
	apacheConfLocation: "/etc/httpd/conf/httpd.conf"


These are the nginx equivalent. There are not allot of these yet

	nginxErrorLog: /var/log/nginx/error.log
	nginxAccessLog: /var/log/nginx/access.log
	nginxConfLocation: /etc/nginx/nginx.conf


Dependencies
------------

None

Example Playbook
----------------

    - name: Setup webserver
      hosts: all
      roles:
        - ggiinnoo.webserver

License
-------

BSD

Author Information
------------------

    Creator: Gino Jansen
    Website: www.ginojansen.nl
