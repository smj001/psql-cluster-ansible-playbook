In this playbook, the variables postgres_user, postgres_db, and postgres_password are defined in the vars section and can be overridden at runtime using the --extra-vars command-line option or by defining them in an inventory file or group_vars file.

The playbook installs PostgreSQL, updates the postgresql.conf and pg_hba.conf files with the appropriate settings, creates a PostgreSQL cluster, creates a database and user, waits for PostgreSQL to start, and performs a cluster health check by running a simple SQL query. Finally, the health check result is displayed using the `

```
ansible-playbook -i inventory.ini ansible.yml --extra-vars "db_username=myuser db_name=mydatabase db_password=mypassword"
```