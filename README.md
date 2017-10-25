# Redmine example for Platform.sh

This project provides a starter kit for a Redmine instance  hosted on Platform.sh. It is primarily an example, although could be used as the starting point for a real project.

## Starting a new project

To start a new project based on this template, follow these 3 simple steps:

1. Clone this repository locally.  You may optionally remove the `origin` remote or remove the `.git` directory and re-init the project if you want a clean history.
 
2. Create a new project through the Platform.sh user interface and select "Import an existing project" when prompted.

3. Run the provided Git commands to add a Platform.sh remote and push the code to the Platform.sh repository.

That's it!  You now have a working Redine instance you can build on.

** CAVEAT**  Redmine creates by default an admin user with "admin" as password; This is bad. And you should immediately change it.

You can do so easily by running the following command (oh and please change  `mysuperstrongpassword`):

`platform ssh 'echo "u=User.find_by_login(\"admin\");u.password=\"mysuperstrongpassword\";u.save!" |rails c'`

## For reference: changes from upstream

Changes from the  upstream Redmine repository (https://github.com/redmine/redmine)

Added the three Platform.sh configuration files:

*  .platform.app.yaml
* .platform/services.yaml
* .platform/routes.yaml

Changed .gitignore so we can commit configuration files that are ignored by default (this is OK in Platform.sh because secrets are generated in the environment )

* .gitignore

Committed: 

* config/configuration.yml 
* config/database.yml 
* config/secrets.yml

And lastly added the `platform_sh_rails` gem and `unicorn` to the Gemfile, generated and committed the lockfile.

* Gemfile
* Gemfile.lock


