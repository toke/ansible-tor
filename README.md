# Tor Hidden Services

A role to configure a tor hidden service

## Requirements

_None._

## Role Variables

##### ***Mandatory***:
* **dir**: Location to store the Hidden service configuration
* **port**: Port to be exposed in the TOR-Network
* **source**: The ip-address and port of the service to be exposed

To support version 3 onion services add **version**: 3 to the hidden_service
configuration.

##### ***Optional***:
| Name | Description | Default Value |
| :--- | :---------- | :------------ |
| tor_become | whether to become root during the installation | true
| tor_config_dir | Tor configuration file directory | /etc/tor
| tor_root_group | Group of the root-User | root


## Dependencies

_None._

## Example Playbook

```yaml
- hosts: servers
  roles:
    role: tor_hidden_services
    hidden_services:
    - dir: /var/lib/tor/ssh-onion
      port: 22
      source: 127.0.0.1:22
    - dir: /var/lib/tor/ssh-onion_v3
      port: 22
      source: 127.0.0.1:22
      version: 3
    - dir: /var/lib/tor/https-onion
      port: 443
      source: 127.0.0.1:443
```

## License

MIT License

## Author Information

* [Toke](https://github.com/toke)
* [Madonius](https://github.com/madonius)
