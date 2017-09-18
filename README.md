# Ansible role for tor hidden services

Example configuration:


```ỳaml
---
hidden_services:
  - dir: /var/lib/tor/ssh-onion
    port: 22
    source: 127.0.0.1:22
```
