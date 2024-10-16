# Deploying Python Web Application with Ansible

This Ansible playbook automates the deployment of a Python web application using Flask, backed by a MySQL database. It streamlines the setup process by handling all necessary configurations, installations, and service management.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Playbook Overview](#playbook-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Example Inventory File](#example-inventory-file)
- [Configuration](#configuration)
- [Getting Started](#getting-started)

## Introduction

This playbook is designed for users who want to quickly deploy a Python web application with a MySQL backend on a Linux server. It sets up the required Python environment, installs necessary packages, and configures the MySQL database.

## Prerequisites

Before you begin, ensure you have the following:

- **Ansible**: Installed on your control machine.
  ```bash
  sudo apt-get install ansible

# Playbook Overview

This playbook automates the setup of a Python application with a MySQL database on a target system. Below is a detailed overview of the tasks performed by the playbook.

## Tasks Performed

1. **Enable Universe Repository**
   - Enables the Universe repository to access community-maintained software packages.

2. **Update APT Cache**
   - Updates the APT package cache to ensure the latest package versions are available for installation.

3. **Install Python 3 and Dependencies**
   - Installs Python 3 along with its necessary dependencies.

4. **Create a Virtual Environment**
   - Creates a virtual environment for the application to manage dependencies in isolation.

5. **Upgrade PIP**
   - Upgrades PIP within the virtual environment to the latest version.

6. **Install PyMySQL Package**
   - Installs the PyMySQL package, enabling interaction with MySQL databases using Python.

7. **Install MySQL Server and Client**
   - Installs both MySQL server and client for database management and connectivity.

8. **Manage MySQL Service**
   - Starts the MySQL service and ensures it runs on system startup.

9. **Create Databases**
   - Creates two databases: `bobdata` and `employee_db`.

10. **Create MySQL User**
    - Creates a MySQL user named `bob` with full privileges to manage the databases.

11. **Install Flask and Flask-MySQL**
    - Installs the Flask web framework and Flask-MySQL extension for web application development and MySQL connectivity.

12. **Copy Application Source Code**
    - Copies the application source code (`app.py`) to the target system.

13. **Start Flask Web Server**
    - Starts the Flask web server to host the application.

# Installation

## Clone the Repository
1.  Replace `<repository-url>` with the actual URL of your repository.
 
    ```bash
    git clone <repository-url>
    cd <repository-directory>

2. Ensure SSH Access: Verify that you have SSH access to your target hosts.
3. Edit the Playbook (if necessary): Open the deploy_python_web_app.yml file and adjust any configurations or variables as needed.

# Usage

To run the playbook, follow these steps:

1.  Modify Your Inventory File

    Create or edit an inventory file to specify your target hosts. Example:

    ```ini
    [all]
    your_target_host ansible_python_interpreter=/usr/bin/python3

2.  Run the Playbook: Execute the following command, replacing deploy_python_web_app.yml with your playbook file name:
    ```bash
    ansible-playbook deploy_python_web_app.yml -i inventory

# Configuration

Before running the playbook, you may want to adjust the following configurations:

### MySQL User and Password
- **User**: Change the MySQL user (currently set to `bob`) as needed.
- **Password**: Update the password for the MySQL user as necessary.

### Database Names
- Modify the names of the databases created:
  - `bobdata`
  - `employee_db`
  
  Change these names if your project requires different database names.

### Application Code
- Ensure that `app.py` is in the correct directory.
- If necessary, update the path in the "Copy source code" task to point to the correct location of `app.py`.

# Getting Started
Follow these steps to set up your environment:

1. Adjust the configurations as described above.
2. Run the playbook to apply the changes.


