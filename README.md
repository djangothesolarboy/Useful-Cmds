Description
---
This is a repo to list a bunch of commands and things I find useful or use often. They range from basic terminal commands to git to Heroku.

Table Of Contents:
---
- [Terminal Commands](https://github.com/djangothesolarboy/Useful-Cmds#terminal-commands)
    - [Terminal - Useful Terminal Commands](https://github.com/djangothesolarboy/Useful-Cmds#useful-terminal-commands)
    - [Terminal - Grep Commands](https://github.com/djangothesolarboy/Useful-Cmds#grep-commands)
    - [Terminal - Misc](https://github.com/djangothesolarboy/Useful-Cmds#misc)
- [Git Commands && Github](https://github.com/djangothesolarboy/Useful-Cmds#git-commands--github)
    - [Github - Setting Up Github](https://github.com/djangothesolarboy/Useful-Cmds#setting-up-github)
    - [Github - Useful Commands](https://github.com/djangothesolarboy/Useful-Cmds#useful-commands)
    - [Github - Branch Forcing](https://github.com/djangothesolarboy/Useful-Cmds#branch-forcing)
    - [Github - Basic Git Flow](https://github.com/djangothesolarboy/Useful-Cmds#basic-git-flow)
- [Heroku Commands](https://github.com/djangothesolarboy/Useful-Cmds#heroku)
    - [Heroku - Environment variables setup](https://github.com/djangothesolarboy/Useful-Cmds#environment-variables-setup)
    - [Heroku - Configuring Heroku to use Postgres database](https://github.com/djangothesolarboy/Useful-Cmds#configuring-heroku-to-use-postgres-database)
    - [Heroku - Pushing to Heroku for first time](https://github.com/djangothesolarboy/Useful-Cmds#pushing-to-heroku-for-first-time)
    - [Heroku - Migrations with Heroku](https://github.com/djangothesolarboy/Useful-Cmds#migrations-with-heroku)
    - [Heroku - In case of rollback](https://github.com/djangothesolarboy/Useful-Cmds#in-case-of-rollback)  
- [Docker](https://github.com/djangothesolarboy/Useful-Cmds#docker)
    - [Docker - Basic Commands](https://github.com/djangothesolarboy/Useful-Cmds#basic-commands)
    - [Docker - Docker Networks](https://github.com/djangothesolarboy/Useful-Cmds#docker-networks)
    - [Docker - Docker Volumes](https://github.com/djangothesolarboy/Useful-Cmds#docker-volumes)
    - [Docker - Docker Images](https://github.com/djangothesolarboy/Useful-Cmds#docker-images)
    - [Docker - Dockerfile](https://github.com/djangothesolarboy/Useful-Cmds#dockerfile)

# Terminal Commands
Useful Terminal Commands
---
- ```touch "filename.filetype"```: create a file as whatever extension you end it as.
    - example: ``` touch cmds.js```
- ```cd ..```: change directory to directory above.
- ```cd ~```: change directory to home/root.
- ```code "filename"```: opens the file name using default editor.
- ```cp "filename" "directory"```: copies the file specified to the directory specified. *if copying file and it exists, it will overwrite existing file*
    - example: ``` cp text.txt /home/documents/ ```
- ```ls```: lists contents of the directory you're currently in.
- ```mv "foldername/filename.txt" "newfolder/filename.txt"```: moves file from one place to another.
    - think of it as "cut" option as in cut and paste.
    - ```mv``` can also rename a directory.
- ```rm "filename"```: removes a file *or* directory.
- ```rmdir "directory"```: removes directory.
- ```curl "url"```: downloads a url to a file on your computer.
- ```curl -o "url-filename" "url"```: allows you to name file you're downloading to your computer.

Grep Commands
---
**Grep is case sensitive**
- ```grep "pattern" "filename"```: will search through file given for the pattern specified.
    - use double quotes for string more than a single word.
- ```grep -r```: search any file in directory for the pattern.
- ```grep -n```: show exact line number for each match.
- ```grep -i```: ignores case of pattern.
- ```grep -c```: returns the number of matches.
    - can be used with ```-r``` to see filenames as well.
- ```man grep```: opens grep's manual page.
- ```man grep | grep -C1 count```: counts the pattern matches on a *man* page.
- ```grep -r "TODO" my_app/ > my-app-todos.txt``` The single ">" operator will create a new file to place output in. Existing content will be overwritten.
- ```grep "my-name" list-of-names.html >> name-locations.txt``` The double > operator will append your output to an existing file (or create a new one if needed).

Misc
---
- ```ls my_directory/ | tee directory_contents.txt```: shows output and writes to a file



# Git Commands && Github
Setting Up *Github*
---
To start working with *Git*, you just need to run the ```git init``` command. It turns the current directory into the *Git* working directory and creates a repository in the ```.git``` (hidden) directory it creates there. You can then start working with *Git*. A repository is a folder whose contents are tracked by *Git*. It is also known as a **repo**.


Useful Commands
---
- ```git status``` shows you what you are doing.
- ```git add .``` adds the current directory(dot) and all of its contents, subdirs and files, to be ready to be saved.
- ```git commit -m "Name the commit"``` will commit the change to the file.
- ```git checkout -b newBranchName``` will create a new branch.
- ```git checkout branchName``` will allow you to look at a different branch.
- ```git checkout master``` will look at the master branch.
- ```git merge "theMERGINGbranch"``` this will merge the branch you wrote with the branch you are currently in.
- ```git checkout -b branchName``` will add a branch and check it out at the same time.
- ```git checkout HEAD^``` will move head to parent of current branch.
- ```git checkout HEAD~2``` will move head to 2 parents back of current branch.


Branch Forcing
---
One of the most common ways I use relative refs is to move branches around. You can directly reassign a branch to a commit with the -f option. So something like:
- ```git branch -f master HEAD~3``` moves (by force) the master branch to three parents behind *HEAD*.


Repo Linked To *Github*
---
Once *github* is linked just run ```git push -u origin master``` to push those changes to *github*.

Basic *Git* Flow
---
- ```git status``` will show you what you are doing -> if you then make a change in the file you can type git status again and it will show if you have modified the file.
- ```git add .``` adds the current directory(dot) and all of its contents, subdirs and files, to be ready to be saved.
- ```git commit -m "Some text"``` commits the change to that branch.
    - ```git commit -am "Commit message"``` will add the directory and add a commit message in one command -> only works with *updating* to files, **not** uploading *new* files.
- ```git push -u origin master``` can also push a different branch to *Git*; replace master with the branch's name.
    - ```git push``` can also do this shorthand to push once you've pushed to the repo already.




# Heroku
Environment variables setup:
---
Navigate to the **Settings** tab to ```Reveal Config Vars``` and set the environment variables needed to run the application. For example, on deadreads inside of the ```.env``` file we used ```SESSION_SECRET``` with a key, you would do the same there:
```
key: SESSION_SECRET
value: adfad-adfadsf-sfdfasd-adfadf
```
Key would be in the left field, value in the right.

Configuring Heroku to use Postgres database:
---
If using dotenv package with ```.sequelizerc``` file update the ```config/database.js``` file with ```production``` key. It should look like this:
```
module.exports = {
  development: {
    username,
    password,
    database,
    host,
    dialect: 'postgres',
  },
  production: {
    use_env_variable: 'DATABASE_URL',
    dialect: 'postgres',
    seederStorage: 'sequelize',
  }
};
```

With Sequelize CLI's config.json:
```
"production": {
  "dialect": "postgres",
  "seederStorage": "sequelize",
  "use_env_variable": "DATABASE_URL"
}
```

Pushing to Heroku for first time:
---
- Log into heroku first -> ```heroku login```
- Add a new remote to Github configuration ->```heroku git:remote -a app_name```
- Add changes -> ```git add .```
- Commit changes with a message -> ```git commit -m "Commit message"```
    - Commit and add -> ```git commit -am "Commit message"```
- Push to heroku -> ```git push heroku```
    - Push different branch -> ```git push heroku other_branch:master```

Migrations with Heroku:
---
- Migrate -> ```heroku run npm sequelize-cli db:migrate```
- Seeding -> ```heroku run npm sequelize-cli db:seed:all```

In case of rollback:
---
- Undo seed -> ```heroku run npm sequelize-cli db:seed:undo:all```
- Undo migration -> ```heroku run npm sequelize-cli db:migrate:undo:all```
- Re-migrate -> ```heroku run npm sequelize-cli db:migrate```
- Re-seed -> ```heroku run npm sequelize-cli db:seed:all```


# Docker

Basic Commands:
---
- `docker -v`: displays version number
- `--name container-name`: names the container
- `-p 80:80`: runs the container on published port 80
- `-d -p 80:80`: runs the container on port 80 in the background(`-d` means detach)
- `docker container ls`: running containers
- `docker container ls -a`: **all** running containers
- `docker container rm container-name`: removes container(can use container name or container id)
- `docker container stop container-name`: stops the container from running
- `docker container start container-name`: starts the container
- `docker container inspect container-name`: information about container, has status, port, etc
- `docker container stats`: information about resources containers are using(that are running on docker machine)
- `docker container top container-name`: displays current processes container is running


Docker Networks:
---
- `docker network ls`: lists networks running
- `docker network create network-name`: creates a network with a name
- `docker container run --name container-name -d --net network-name nginx:alpine`: creates a container on the network specified in the background (alpine is a specific version of nginx that has ping installed)
- `docker container run -p 80:80 -d --name container-name --mount type=bind,source="$(pwd),target="/usr/share/nginx/html" nginx`: points to physical spot in your computer
	- `--mount type=bind`: binding local file to container
	- `source="$(pwd)"`: says the source is the current directory
	- `target="/usr/share/nginx/html"`: is location where html file is located on container
- `docker container exec -it nginx bash`: opens up bash in container
    - `-t`: simulates a terminal (like SSH)
    - `-i`: keeps a session open to receive terminal input
- `docker container run -d --net network-name --net-alias network-alias`:
    - `-net network-name`: specifies the network name
    - `--net-alias network-alias`: alias the network like `localhost` is `127.0.01`
- `docker container run --net network-name alpine nslookup network-alias`: `nslookup` returns any ip address it finds on the specified network alias and the name of the network

  
Docker Volumes:
---
- `docker container run -d --name container-name -e MYSQL_ALLOW_ROOT_PASSWORD=true --mount source="volume-name",target="/volume-name" nginx`: 
	- `-e`: flag is an environment variable
	- `MYSQL_ALLOW_ROOT_PASSWORD=true`: tells it not to configure a password
	- `--mount source="volume-name"`: tells the name of the volume to use
- `docker volume rm volume-name`: removes volume



Docker Images:
---
- `docker image ls`: lists all the images on your computer
- `docker image tag image-name username/image-name:tag-name`: will change the tag of an image specified
- `docker image inspect image-name`: will inspect image specified and displays information
- `docker image history image-name`: displays the layers that make-up the image


Dockerfile:
---
- `docker build . -t image-name:tag-name`: builds an image from a Dockerfile
    - `.`: says current directory
    - `-t`: allows a named tag you specify
- `docker build . -f /path/to/a/Dockerfile`: builds an image from a Dockerfile in specified directory
    - `-f`: flag that builds image from a different directory
- `FROM node:15-alpine3.12`: builds off node image
- `EXPOSE 3000`: creates a port on `3000`
- `WORKDIR /app`: creates working directory `/app` if it does not exist
- `COPY package*.json index.html ./`: copies `package*.json` & `index.html` into `/app`
- `RUN npm install`: runs npm install inside image
- `COPY . .`: copies everything in current directory from `.`(current directory locally) to `.`(image)
- `CMD ["npm", "start"]`: runs `npm start`