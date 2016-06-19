ASSUMPTIONS:
- this is being ran from a secured management box (lol)

TODO:
- ~~set up elasticsearch~~
- ~~logstash~~
- ~~kibana~~ / nginx TODO: right now ssh port forwarding sure it's grand
- add ssl to logstash
- ~~add 2nd server (staticwww)~~
  - nginx
  - ~~filebeat~~ TODO: need to expose logstash on 10.10.1.249
  - TODO: need to set host_vars for filebeat to send logs to
  - tests
- tests to ensure filebeat talks to logstash
- local management of mgmt box
- updates
- fail2ban
- haproxy
  - letsencrypt
  - filebeat
  - tests
  - logging and staticwww
- ensure all servers have appropriate tests in ansible!
- firewall
  - basics
  - deepen (allow to, from)
  - logging, filebeat
