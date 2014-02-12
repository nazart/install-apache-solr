Solr 4.6.x multi-core Ubuntu/Debian install.sh
----------------------------------------------

This installs the current multi-core Apache Solr 4.6.x in Tomcat 6 on Ubuntu/Debian.

Install
-------
To install without cloning the repository using the default 8080 port:

    curl https://raw.github.com/eosrei/install-apache-solr/master/install.sh | sudo bash -s

To install with the repository:

    git clone https://github.com/eosrei/install-apache-solr.git
    cd install-apache-solr
    (edit the install.sh and change the port or install directories)
    sudo ./install.sh

Clone the repository to test with Vagrant:

    git clone https://github.com/eosrei/install-apache-solr.git
    cd install-apache-solr
    vagrant up

Tested on Ubuntu 12.04LTS and Linux Mint 15; others TBD.

Notes
-----
* The default Tomcat 6 port is 8080. It should be firewalled from external access.
* Only one core is created, additional cores will need to be created manually.
* Drupal specific config files need to be installed manually to:
  $SOLR_INSTALL_DIR/multicore/core0/conf

* A random Apache Download Mirror is choosen and some are slow. It is OK to
  stop(^C) the script and start it again.
* This might work to upgrade between 4.6.x releases. It shouldn't delete data.
  Test it.

Todo
----
* Additional pre-install checks for open port and required tools.
* Support 4.x.x versions as released
* Detect and support Centos/Redhat
* Install Drupal Apache Solr Search or Search API Solr search module configurations
* Setup Tomcat6 Users

More information
----------------
* Solr Multicore details: https://wiki.apache.org/solr/CoreAdmin
