Ansible Playbook: SFTP and LAMP Setup with Multiple Databases
This Ansible playbook automates the configuration of an SFTP server for multiple users, along with setting up a LAMP stack (Linux, Apache, MySQL, PHP) for different databases including MySQL, Redis, and RabbitMQ. It also includes inserting data into these databases via a web server.

Table of Contents:
Description,
Prerequisites,
Usage,
Files,
Variables,
Contributing,
Description,
This playbook performs the following tasks:

Configures SFTP server for multiple users with isolated home directories.
Installs and configures a LAMP stack with Apache, MySQL, and PHP.
Creates MySQL databases, users, and tables, and inserts data via a web server.
Installs and configures Redis for key-value storage with authentication.
Installs and configures RabbitMQ with user authentication and management, and data insertion via a web server.
Prerequisites
Before running this playbook, ensure:

Ansible is installed on the control node.
Inventory file (inventory) is correctly configured.
Necessary roles and dependencies are installed.
Passwordless SSH access to target nodes is set up.
Variables in group_vars/dev are appropriately configured.
Usage
Clone this repository to your Ansible control node.
Configure the inventory file with your target nodes.
Review and adjust variables in group_vars/dev file according to your requirements.
Run the playbook with the following command:
sh
Copy code
ansible-playbook -i inventory play.yml
Follow the prompts to enter necessary information such as SFTP usernames, Redis and RabbitMQ passwords, etc.
Files
ansible.cfg: Ansible configuration file.
group_vars/dev: Variable file for development environment.
inventory: Inventory file listing the target nodes.
mysql.php.j2: Jinja2 template for MySQL configuration and data insertion.
play.yml: Main playbook file containing all tasks.
rabbitmq.php.j2: Jinja2 template for RabbitMQ configuration and data insertion.
redis.php.j2: Jinja2 template for Redis configuration and data insertion.
Variables
Variables are defined in the group_vars/dev file. Key variables include:

SFTP user password (sftp_user_password).
MySQL root and database user credentials.
Redis password (redis_password).
RabbitMQ user credentials (rabbitmq_user, rabbitmq_password).
Contributing
To contribute to this project:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Commit your changes (git commit -m 'Add some feature').
Push to the branch (git push origin feature-branch).
Open a pull request.
