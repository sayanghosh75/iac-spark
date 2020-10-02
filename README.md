# iac-spark
Ansible playbook to install Apache Spark

<!-- This should be the location of the title of the repository, normally the short name -->
# IAC-Spark - Ansible Script to Install Spark

<!-- Build Status, is a great thing to have at the top of your repository, it shows that you take your CI/CD as first class citizens -->
<!-- [![Build Status](https://travis-ci.org/jjasghar/ibm-cloud-cli.svg?branch=master)](https://travis-ci.org/jjasghar/ibm-cloud-cli) -->

<!-- Not always needed, but a scope helps the user understand in a short sentance like below, why this repo exists -->
## Scope

The purpose of this repository is to provide an ansible playbook for installation of Apache Spark on a linux host. The script has been developed using instrustions steps published on different public web-sites.


<!-- A more detailed Usage or detailed explaination of the repository here -->
## Usage

This repository provides a playbook for use with a Linux Host(s). The playbook retrieves the archives for spark and scala, extracts them to a staging directory and installs them to the appropriate paths. The playbook also installs keras, tensorflow, tensorboard, pyspark and Jupyter notebooks and configures the user environment to be able to start this. This playbook doesn't configure any clustering for the spark environment.

Key files:

Uncomment the correct ssh user and key for IBM Cloud or AWS in ansible.cfg

Execution:

Execute ansible-playbook spark-setup.yml

Files:
1. spark-setup.yml: The playbook to call, hosts all the package and destination variables and updates the user path environment
2. spark-extract.yml: Extract the archives into the appropriate directories for installation
3. spark-install.yml: Moves the spark and scala files to the correct directories
4. infra-setup.yml: Ensures firewalld is started
5. jupyter-setup.yml: Configures jupyter notebook to allow access from remote and opens the firewall port
6. python-install.yml: Installs all necessary python packages

Configurations:

ansible.cfg - uncomment the appropriate lines for use with a Public Cloud provider

Cleaning up:
To destroy the provisioned environment, make changes to the script for your own purposes. 

<!-- License and Authors is optional here, but gives you the ability to highlight who is involed in the project -->
## License & Authors

If you would like to see the detailed LICENSE click [here](LICENSE).

- Author: Sayan A Ghosh <sghosh@sg.ibm.com>

```text
Copyright:: 2020-2020 IBM, Inc

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
