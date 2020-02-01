cygwin-role
=========

Installs cygwin on a system, configures user and service to enable ssh access.  You can also define additional users to be added to cygwin.

Requirements
------------

Windows Server 2016

Role Variables
--------------

Variables and default values:

     Installation vars
    	installer_url: https://cygwin.com/setup-x86_64.exe
    	installer_checksum: https://cygwin.com/sha512.sum
    	cygwin_packages:
    	  - curl
    	  - python27
    	  - python27-jinja2
    	  - python27-crypto
    	  - python27-openssl
    	  - python27-setuptools
    	  - git
    	  - vim
    	  - openssh
    	  - openssl
    	  - libssl-devel
    	tmp_dir: C:\cyg_inst\
    	install_dir: C:\cygwin4
    	packages_site: http://ftp-stud.hs-esslingen.de/pub/Mirrors/sources.redhat.com/cygwin/
    
     Configuration vars
    	sshd_service: cyg_sshd
    	sshd_user: cyg_server
    	sshd_user_passwd: pasSw0rD1
    	sshd_user_privileges:
    	  - SeCreateTokenPrivilege
    	  - SeAssignPrimaryTokenPrivilege
    	  - SeIncreaseQuotaPrivilege
    	  - SeServiceLogonRight
    	  - SeDenyInteractiveLogonRight
    	  - SeTcbPrivilege
    	sshd_service_descr: "Sshd Service"
    
     Optional users vars
    	cygwin_users:
    	  - myuser


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: cygwin-role }

License
-------

BSD

Author Information
------------------

slawkaw9@github