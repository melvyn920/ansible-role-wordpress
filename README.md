[![Ansible Galaxy](https://img.shields.io/badge/role-melvyn920.wordpress-blue.svg)](https://galaxy.ansible.com/melvyn920/wordpress)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

Ce rôle Ansible déploie automatiquement un site WordPress avec une base MariaDB sur des hôtes Linux basés sur Ubuntu ou Rocky Linux.

---

- Ansible 2.9+
- Accès root aux hôtes distants
- Groupes `ubuntu` et `rocky` bien définis dans l’inventaire

---

| Variable                   | Description                                | Valeur par défaut     |
|---------------------------|--------------------------------------------|------------------------|
| `wordpress_db_name`       | Nom de la base de données WordPress        | `wordpress`            |
| `wordpress_db_user`       | Utilisateur de la base                     | `example`              |
| `wordpress_db_password`   | Mot de passe de l’utilisateur de la base   | `examplePW`            |
| `wordpress_db_root_password` | Mot de passe root MySQL                  | `examplerootPW`        |

Ajoutez ces variables dans votre playbook ou fichier de vars si vous souhaitez les personnaliser.

---

```yaml
- name: Déploiement WordPress
  hosts: clients
  become: yes
  vars:
    wordpress_db_name: wordpress
    wordpress_db_user: example
    wordpress_db_password: examplePW
    wordpress_db_root_password: examplerootPW
  roles:
    - melvyn920.wordpress
