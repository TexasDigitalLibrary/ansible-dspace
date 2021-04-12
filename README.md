# ansible-dspace

Ansible playbooks to stand up an instance of DSpace 7.x (API and Angular Frontend)

## Requirements

* [Vagrant](https://www.vagrantup.com/)
* [VirtualBox](https://www.virtualbox.org/)

## Usage
1. Install Vagrant and VirtualBox
2. `git clone https://github.com/TexasDigitalLibrary/ansible-dspace && cd ansible-dspace`
3. `cp site_vars.yml.example site_vars.yml` and configure appropriately
4. `vagrant up`

## Environment

* Amazon Linux 2
  * Apache 2.4
  * Tomcat 9.0
  * PostgreSQL 11.5
  * Shibboleth 3.2
  * Solr 8.8.1
  * Fuseki 4.0.0
  * Node.js 14.16.1
  * PM2 4.5.6
  * DSpace 7.x (API and Angular Frontend)

## Notes

- Vagrant is configured to forward Apache and Tomcat to their default ports on your system, which may not be available if you have those services running already. They should be stopped locally so that Vagrant can forward to the defaults in order for Angular and the API to communicate in the VM.

## License

This code is licensed under the [GNU General Public License (GPL) V3](https://www.gnu.org/licenses/gpl-3.0.en.html).

## Contact

For questions, comments or assistance please contact support@tdl.org.
