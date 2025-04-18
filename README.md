# ansible-role-wordpress

Ce rôle Ansible installe WordPress et MariaDB sur des serveurs Linux (Ubuntu ou Rocky Linux).

## Variables

- `wordpress_db_name`: Nom de la base de données (default: wordpress)
- `wordpress_db_user`: Utilisateur de la base (default: wpuser)
- `wordpress_db_password`: Mot de passe (default: secret)

## Utilisation

```yaml
- hosts: clients
  become: yes
  roles:
    - ansible-role-wordpress
