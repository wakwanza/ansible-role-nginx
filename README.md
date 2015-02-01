nginx
=========

nginx role to provide a secure ssl connection with backend health checks provided by consul.io .Extra security features baked into the default nginx binary include naxsi and more featured headers module for obfuscation and hashing of links.Extra artillery idp/ids installed.
Fail2ban with nginx-local jails.Custom ssl configuration for A-Grade at Qualys ssl-check.Monit daemon for keep alive of the nginx process and autoreload in cse of errors.

Requirements
------------

Environment must be using consul for service discovery, both for the current nginx node and the backends to be balanced.SSL certificates in certs directory , private and public fragments , with the public fragment chained with its intermediate certs.


Role Variables
--------------

<table>
    <tr>
        <td>{{ repo.epel }} </td> <td>EPEL repo url default (leaseweb mirror)</td>
    </tr>
        <tr>
        <td>{{ nginx.custom }} </td> <td> rpm location for custom nginx build</td>
    </tr>
    <tr>
        <td>{{ nginx.internal_range }} </td> <td> Internal subnet range  for backend services</td>
    </tr>
    </tr>
    <tr>
        <td>{{ consul.binary }} </td> <td> Consul binary zip for x86_64</td>
    </tr>
    <tr>
        <td>{{ consul.template }} </td> <td> Consul-template binary zip for x86_64</td>
    </tr>
     <tr>
        <td>{{ artillery.homebase }} </td> <td> Ranges of ips to whitelist</td>
    </tr>
    <tr>
        <td>{{ artillery.alert_email }} </td> <td> Email address for alerts to be sent to</td>
    </tr>
    <tr>
        <td>{{ artillery.custom_ports }} </td> <td> Custom ports to monitor with artillery</td>
    </tr>
</table>


Dependencies
------------

.


Example Playbook
----------------

    - hosts: webservers
      roles:
         - { role: wakwanza.ansible-role-nginx }

License
-------

BSD

Author Information
------------------

wakwanza.
