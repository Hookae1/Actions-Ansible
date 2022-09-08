# DevOps Task

## Technical Task of implementing a Deployment Pipeline, using ansible and GitHub Actions for invocation.

Our team wants to create a self-service option for Python virtual environments to developers using an interface, they are familiar with: requirements.txt and git.
For this matter we want to create a github Actions pipeline, that triggers an ansible playbook on servers (in this case, please just use localhost).

You can assume the following:

- *The runners are already configured (for testing please use github provided runners)* 
- *The operating system is a debian based flavour.*
- *The vens will be installed in /opt/python_venvs/*
- *The name of the txt file (requirements file) will be the name of the virtual environment*
- *The pipeline needs to be able to:*
  * *Create multiple venvs, depending on how many txt files are in the repository.*
  * *Only executethee installation of packages on changed files.*
 
Please make sure, when you are testing, that the action needs to install ansible + python as a requirement. If you are using a self hosted runner, then you can manually provide this yourself, we will take care of a test in our environment. 

## Solution
All mentioned points in the task are respected and fully done.

[GitHub Actions-pipeline](.github/workflows/actions-pipeline.yml) consists of two jobs:
- *Validate - validation of [ansible-playbook](ansible/python.yml) file by using ansible-lint plugin*
- *deployAnsible - installing (python, ansible) & deploying ansible-playbook.* 
