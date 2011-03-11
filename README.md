This is an example [whiskey_disk](https://github.com/flogic/whiskey_disk) configuration repo.

When you do a deployment with whiskey_disk, you have the option of using a 
configuration repository to store environment-specific configuration files,
sensitive data, or really anything else that doesn't belong in your application's
source control. The most obvious example is probably the `database.yml` file
in a rails application.

**NOTE:** This repo assumes you have the following in your `deploy.yml` in your application:

    my_app_name:
      staging:
        domain:
        - name: "user@my.server.u.r.i" 
          roles:
          - "db"
        deploy_to: "/var/www/my_app_name"
        deploy_config_to: "/var/www/whiskey_disk_config_example"
        repository: "git@github.com:username/my_app_name.git"
        branch: "staging"
        config_repository: "git@github.com:username/whiskey_disk_config_example.git"
        config_branch: "master"
        config_target: "staging"
        rake_env:
         RAILS_ENV: 'staging'

