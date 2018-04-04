ansible-role-simplesamlphp-idp
==============================

This role installs and configures a simple identity provider (IdP) which can
be used for testing applications that make use of SAML authentication. A
service provider (SP) is also installed for convenience (can be used to ensure
that the IdP is working as expected).

Usage
-----
In order to use the role, add the following to the `requirements.yml` located
inside the ansible folder (create the `requirements.yml` file if it does not
exist):

```
- src: git+https://github.com/magenta-aps/ansible-role-simplesamlphp-idp.git
  version: master
  name: simplesamlphp
```

Installing the role
-------------------
Do the following to install the role in your project:

```
$ cd /path/to/ansible-project
$ ansible-galaxy install -r requirements.yml
```

This will install the role in your roles folder.

Role Variables
--------------
You need to specify the following variables in the appropriate `host_vars`-file:

```
idp_hostname: idp.example.org
sp_hostname: idp.example.org
```

NOTE: currently, the role installes a couple of pre-configured self-signed SSL
certificates corresponding to the hostnames `idp.example.org` and
`sp.example.org`, respectively. *TODO:* add tasks to create and install
self-signed certificates based on the `idp_hostname` and `sp_hostname`
variables.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - simplesamlphp


Author Information
------------------

https://github.com/andreaskring
