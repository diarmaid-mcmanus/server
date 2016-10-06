https://gist.github.com/scarolan/5782025

ASSUMPTIONS:
- this is being ran from a secured management box (lol)
- bastion.yml now locks down the local box using fail2ban.

HOW TO USE:
- pip install debops
- ansible-playbook -k -K -s main.yml

TODO:
- ~~kibana~~ / nginx TODO: right now ssh port forwarding sure it's grand
- add ssl to logstash
- local management of mgmt box
- ~~updates~~
- fail2ban
- ~~haproxy~~
  - letsencrypt
  - ~~filebeat~~
  - multiple domains
- ensure all servers have appropriate tests in ansible!
- firewall
  - basics
  - deepen (allow to, from)
  - logging, filebeat
- tests - monit, sensu, magiot, observium?
