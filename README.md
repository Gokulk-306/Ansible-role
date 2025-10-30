# Apache2 Role

This Ansible role installs and configures **Apache2** on managed nodes.  
It also replaces the default Apache web page with a custom HTML file located in the role’s `files/` directory.

---

## Requirements

- Ansible 2.9 or later  
- Managed nodes must be running a Debian/Ubuntu-based OS  
- Python should be installed on the target machines (Ansible requirement)

---

## Role Variables

You can define or override these variables in your playbook or inventory:

| Variable Name | Default Value | Description |
|----------------|----------------|-------------|
| `apache_package` | `apache2` | Name of the Apache package to install |
| `html_src` | `index.html` | Name of the custom HTML file located in the `files/` directory |
| `html_dest` | `/var/www/html/index.html` | Destination path for the HTML file on the managed node |
| `apache_service` | `apache2` | Apache service name (can vary for other OS families) |

---

## Dependencies

None.

---

## Example Playbook

```yaml
- name: Install and configure Apache2
  hosts: webservers
  become: yes
  roles:
    - role: apache2
      vars:
        apache_package: apache2
        html_src: custom.html
        html_dest: /var/www/html/index.html

License

BSD

Author Information

Developed by Gokul K
Aspiring DevOps Engineer | DevOps Enthusiast