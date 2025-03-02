# 🚀 Projet de Déploiement Automatisé WordPress

## 📚 Table des Matières

- [Description](#-description)
- [Prérequis](#-prérequis)
- [Installation](#-installation)
- [Structure du Projet](#-structure-du-projet)
- [Utilisation](#-utilisation)
- [Tests](#-tests)
- [Contribution](#-contribution)
- [Licence](#-licence)

## 📖 Description

Ce projet vise à automatiser le déploiement d'un site WordPress sur un serveur cible en utilisant Ansible, AWX et une collection de rôles personnalisée. Il comprend deux composants principaux :

1. Un projet Ansible pour gérer le déploiement
2. Une collection Ansible pour centraliser et modulariser les rôles

## 🛠 Prérequis

- Python 3.8+
- Ansible 2.9+
- Git
- Docker (pour les tests Molecule)
- Accès SSH aux machines cibles

## 🚀 Installation

1. Clonez le dépôt :

```bash
git clone https://github.com/CalixteManaud/ansible-worpdress-project.git
cd ansible-wordpress-project
```

2. Créez un environnement virtuel Python :

```bash
python3 -m venv venv
source venv/bin/activate
```

3. Installez les dépendances :

```bash
pip install -r requirements.txt
```

4. Installez la collection Ansible :

```bash
ansible-galaxy collection install -r requirements.yml
```

## 📁 Structure du Projet

```bash
.
├── README.md
├── ansible.cfg
├── inventories
│   └── production.yml
├── playbooks
│   └── playbook.yml
├── requirements.txt
└── requirements.yml
```

## 🎮 Utilisation

1. Configurez votre inventaire dans `inventories/production.yml`

2. Lancez le playbook :

```bash
ansible-playbook -i inventories/production.yml playbooks/playbook.yml
```

3. Pour utiliser AWX :

- Créez un nouveau projet dans AWX pointant vers ce dépôt
- Configurez un modèle de job utilisant le playbook `playbook.yml`
- Lancez le job depuis l'interface AWX

## 🧪 Tests

Pour lancer les tests Molecule sur les rôles de la collection :

```bash
cd ynov/general/roles/nom_du_role
molecule test
```

Répétez pour chaque rôle (post_installation, web_server, mariadb, wordpress).

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une issue ou à soumettre une pull request.

## 📄 Licence

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.
