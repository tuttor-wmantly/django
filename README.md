# Django

These instructions are for Ubuntu 16.04, they should work with any Ubuntu/Debian based distro( Milage may vary )

## System packages

We will need several Linux packages to develop Django on our system.

```bash
sudo apt update && sudo apt upgrade
apt get git python3 python3-dev python3-pip libpq-dev postgresql postgresql-contrib
```

And we will need virtual env globally installed.

```bash
sudo pip3 virtualenv
```

It is recommended that ONLY virtualenv be installed globally.

## Starting Python projects

All python development ( Django included ) should be conducted in a dedicated directory and virtualenv. Move to your development folder( ~/dev )
and make a directory for this project.

Project names should ONLY contain letters, numbers, and underscores( _ ) and start with a letter.  NO SPACES OR DASHES!!!

```bash
cd ~/dev
mkdir <project name>
cd <project name>
virtualenv env
```

At this point the project is ready, but not for development.

## Developing Python projects

Every time you start working on a project, you need to move to the projects folder and enter the virtual environment

```bash
cd ~/dev/<project name>
source env/bin/activate
```

If the project has a `requirments.txt` file, you need to install it to your local virtual env has the required packages

```bash
pip -r requirments.txt
```

Now you are ready to work on this project.

## Installing Python packages.

Once you are in the virtual environment you can install needed packages, like Django with the `pip` command

```bash
pip install django-toolbelt
```

We also need to keep track of what packages are installed and their versions.

```bash
pip freeze > requirments.txt
```

##  Starting a Django project

This only needs to be done once, at the beginning of the project. We will use the `django-admin` utility to build a simple base project. From with in your project directory and an active virtual environment, run this command.

```bash
django-admin startporject project .
```

We have set the name of the project to be 'project'. This is very important will make your life easier down the road. It was a mistake from the Django team early on to even allow this to be something different.
