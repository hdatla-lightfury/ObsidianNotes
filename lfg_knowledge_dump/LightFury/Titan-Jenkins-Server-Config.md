
DockerFile
-> The core docker 
-> installs jenkins lts and jdk17 
-> swithces to root(power user)
->  installs python3 specific to the linux distribution
 -> gets a GPG key, and puts the required packages need to be downloaded with GPG key and puts in docker.list
 -> installs docker-cli and for jenkins to interact with docker and run commands.
 -> switches to jenkins user
 -> installs blueocean(fancy UI), jenkins and perforce SCM plugins for pipelines 
 -> configuration as code plugin , allows you to manage jenkins configuration with yaml files.
 -> installs perforce cli tool for it to work 
 -> adds jenkins user to user group and then swtiches to jenkins user 
 -> jsonpath plugin to read yaml configuration files.
 
 
 
 ~~docker_build.ps1~~ 
 ~~-> gets the name of the docker image and builds it(container image)~~ 
 ~~-> optional(push image to docker registry)~~
 ~~->~~ 

~~docker_run.ps1~~ 
~~-> does what docker_build does ? (wtf)~~
~~-> reads the credentials from the environment file for perfoce and  passes it to to dockerfile.~~
~~-> runs the docker container created from the dockerfile with two diff ports assigned and optionally mounting the hosts docker socket to the container.~~


~~init_git_session.sh~~
~~-> git personal access token manager.~~

~~jenkins_get_admin_password.ps1~~
~~-> gets the initial admin setup in the (current) running docker container.~~

windows-agent/DockerFile
For P4 titan source win job.
TBR later



run_server.sh
-> main and only file i beleive ?

loads .env file for perforce credentials.
takes a name for docker suggestion and builds the image


runs the docker container with a docker volume created with socket binding as optional and adding docker group to avoid headaches with permissions
-> the windows dockerfile runs with perforce credentials and once the docker container is successfully run, gives you initial admin password.
List of improvements
-> Drop Down With revision number ?
-> Rebuild Last Successful Build ?
-> User Login/Credentials ?
-> Build Logs Persistance ? 












.













