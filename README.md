# Yii basic app

This project aims to show how you can separate your environments. 
To do that, we used a [yii](https://www.yiiframework.com/) application.


## How to install

1. Add config to the docker-compose.yml file

Let's say we want to have a new environment. You can add it by adding this configuration to the docker-compose.yml file in the `services` configuration.

```
services:
    service_name:
        build: path_to_dockerfile
        volumes:
        - path_to_directory:/app:rw
        ports:
        - unused_port:8080
```

2. Run these commands

> 1. `git clone https://github.com/1000x-Developers/basic_yii_app path_to_directory`
> 2. `cd path_to_directory`
> 3. `docker compose run service_name composer install`
> 4. `docker compose up service_name -d`

## How to manage your versions

If you want to work on a new feature or fix a bug you can create a new dedicated branch. Let's say we want to change the title of one of our views.

1. Switch to a new branch: `git checkout -b branch_name`
2. Make your modifications
3. If you want to go back to another branch without commiting you work. You can stash it `git stash` and unstash it if you want to get it back `git stash apply`.
4. If you want to commit (and perhaps push) you can do so by using the `git commit` command and then do `git push --set-upstream origin branch_name`. From there you will be able to create a pull request if it is not already set up.
5. Once merged you may delete the remote branch and the local branch.
6. Pull on main and you can start over. :)
