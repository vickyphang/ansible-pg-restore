# Ansible PostgreSQL Restore Playbook ♻️

This Ansible playbook is designed to simplify the process of restoring a PostgreSQL database from a SQL dump file. By automating the restoration process, you can save time and reduce the risk of human error.

### Key Features
- Automation: Streamlines the restoration process, eliminating manual intervention.
- Flexibility: Configurable to work with different PostgreSQL versions and database configurations.
- Error Handling: Incorporates error handling mechanisms to ensure a robust restoration process.
- Security: Employs best practices for secure database operations.

### How to Use
1. Clone the Repository
    ```bash
    git clone https://github.com/your_username/ansible-pg-restore.git
    ```
2. Configure the agent
    ```bash
    # Install apt packages
    apt install ansible python3-pip python3-dev  postgresql-client-common postgresql-client -y

    # Install ansible collections
    ansible-galaxy collection install community.postgresql
    ```
3. Configure the Playbook
    - Edit the `vars.yml` file to specify the following:
        - PostgreSQL host
        - PostgreSQL port
        - PostgreSQL username
        - PostgreSQL password
        - Database name to restore
        - SQL dump file name
    - Edit the inventory file
        - `ansible.cfg`
            ```
            [defaults]
            inventory = hosts.ini
            host_key_checking = false
            ```
        - `host.ini`
            ```
            [server]
            10.0.0.11
            ```
4. Run the Playbook
    ```bash
    ansible-playbook pg-restore.yml
    ```