https://gist.github.com/scarolan/5782025

ASSUMPTIONS:
- this is being ran from a secured management box (lol)
- bastion.yml now locks down the local box using fail2ban.

HOW TO USE:
- apt install git python python-pip sshpass
- git clone git://github.com/ansible/ansible.git --recursive (see ansible docs)
- get the latest vagrant from https://www.vagrantup.com/downloads.html
- install virtualbox from https://www.virtualbox.org/wiki/Linux_Download
- pip install pyyaml jinja2 debops
- add files/hosts to /etc/hosts
- ansible-galaxy install debops.fail2ban
- ansible-galaxy install geerlingguy.haproxy
- vagrant up
- ansible-playbook -k -K -s main.yml

TODO:
- ~~kibana~~ / nginx TODO: right now ssh port forwarding sure it's grand
- add ssl to logstash
- ~~local management of mgmt box~~ bastion.yml -K --connection=local
- ~~updates~~
- ~~fail2ban~~
- ~~haproxy~~
  - letsencrypt
  - ~~filebeat~~
  - ~~multiple domains with sni~~ ish
- Alaveteli
- Postfix
- Postgres
- ensure all servers have appropriate tests in ansible!
- firewall
  - deny all communication between hosts except required
    - haproxy - servers, all - logging, etc.
    - enable logging of firewall rule alerts
  - logging, filebeat
- tests - monit, sensu, magiot, observium?
