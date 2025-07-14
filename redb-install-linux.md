# Installation instruction for LINUX 


## Downloaded package

```bash
# Install PostgreSQL 17 as prerequisite (if not installed already)
sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh
sudo apt update
sudo apt -y install postgresql

# Create an admin user that the application can use for initialization
sudo -u postgres psql
CREATE USER your_admin_user WITH ENCRYPTED PASSWORD 'your_admin_password' CREATEDB CREATEROLE LOGIN;
exit

# Install Redis Server as a prerequisite (if not installed already)
sudo apt install redis-server

# For arm64-based systems
Go to https://download.redb.co and download the right package from the 'latest version'
Direct link to the arm64 directory https://download.redb.co/linux/latest/arm64/

# For amd64-based systems
Go to https://download.redb.co and download the right package from the 'latest version'
Direct link to the amd64 directory https://download.redb.co/linux/latest/amd64/
```

## Initializing the installation

```bash
# Initialize the reDB installation
./redb-supervisor --initialize

# If prompted, provide the PostgreSQL details
Enter PostgreSQL username [postgres]: your_admin_user
Enter PostgreSQL password: *your_admin_password*
Enter PostgreSQL host [localhost]: 
Enter PostgreSQL port [5432]: 

# Select "y" to create the default tenant and user - required for a fresh install
Would you like to create a default tenant and user? (y/N): y

# Enter the details of the default tenant and user
Enter tenant name: tenant_name
Enter admin user email: you@domain.com
Enter admin user password: *your_new_login_password*
Confirm password: *your_new_login_password*

# Initialization is complete, ready to start the application
./redb-supervisor

# The application can be run in the background as a service
```

## Using the application for the first time

```bash
# Logging in
redb@redb-demo:~$ ./redb-cli auth login
Username (email): demo@redb.co
Password: 
Hostname (default: localhost:8080): 
Tenant URL: demo
Successfully logged in as demo@redb.co
Session: reDB CLI (ID: session_1752410814767386264_1nkJhJM4)

Select workspace (press Enter to skip): 
No workspace selected. Use 'redb-cli select workspace <name>' to select one later.
redb@redb-demo:~$ 

# Creating your first workspace
redb@redb-demo:~$ ./redb-cli add workspace
Workspace Name: demo
Description (optional): reDB demo workspace
Successfully created workspace 'demo' (ID: ws_0000019803D4CBCEBCA9C6AB2D)
redb@redb-demo:~$

# Selecting the current workspace
redb@redb-demo:~$ ./redb-cli select workspace demo
Selected workspace: demo (ID: ws_0000019803D4CBCEBCA9C6AB2D)
redb@redb-demo:~$
```
