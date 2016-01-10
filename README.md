# iodine (Ansible Role)

## Description

This role installs and configures the [iodine](http://code.kryo.se/iodine/) IP over DNS server.

This server allows you to circumvent dns-based internet gateways like at some airports and hotels, provided you have a publicly resolvable IP address and the iodine server running.

## Requirements

* Ansible
* iodine client

## Variables

### in main.yml

* `iodine_password: CHANGE_ME` - The password the iodine client needs to connect
* `iodine_private_ip: 10.0.10.1` - The address the server will use in the tunnel
* `iodine_server_dns: "ns.{{ ansible_fqdn }}"` - The DNS name the server will use

## Example Playbook

- hosts: all
  sudo: true
  roles:
    - role: ansible-iodine

## Local Testing

For local testing you can use vagrant and Virtualbox.

To connect from a client, either on the vagrant box itself, or from
your machine, use:

`sudo iodine -f -r <IP_ADDRESS> -P CHANGE_ME <FQDN>`

Using the default values, this would be:

`sudo iodine -f -r 172.19.22.23 -P CHANGE_ME ns.iodine.172.19.22.23.xip.io`

To test if your iodine machine is configured properly, go to the [Iodine troubleshooter](http://code.kryo.se/iodine/check-it/) and enter your hostname.

## Contributors

Thanks to [yarrick](https://github.com/yarrick/iodine) for writing and maintaining iodine.
Pull requests and support for more OSs are welcome.

## License and Author

* Author:: Matt Urbanski <matt@iflowfor8hours.info>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
