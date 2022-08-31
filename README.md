## INTRODUCTION
It's a compose file that contains a pre-configuration of Self-managment Gitlab Community Edition

## REQUIREMENTS
- Docker Installed

## INSTALATION PROCESS
In the directory with compose file execute:
- sudo docker compose up -d
Our GitLab is available at defined base url, example: http://localhost:8080. 
## REGISTER GITLAB RUNNER (For CI/CD)
1. To use the GitLab runner in GitLab, you need to configure it. For correct configuration, we will need a token copied from the    portal. To do this, go to the address: http://localhost:8080/admin/runners (Consider your context in base url) and click the Copy token button.
2. In the next step, it goes to the console and run the following command: sudo docker run --rm -it -v /srv/gitlab/gitlab-runner/config:/etc/gitlab-runner gitlab/gitlab-runner register;
3. Enter your GitLab instance URL (also known as the gitlab-ci coordinator URL), as Runner and Gitlab are on the same machine we can use the localhost, example: http://localhost:8080;
4. Enter the token you obtained to register the runner;
5. Enter a description for the runner;
6. Enter the tags associated with the runner, separated by commas. (optional) ;
7. Enter any optional maintenance note for the runner;
8. Provide the runner executor. For most use cases, enter docker.
9. If you entered docker as your executor, you are asked for the default image to be used for projects that do not define one in .gitlab-ci.yml.
10. Then we add new line to the end of the runner configuration: network_mode = “gitlab-network” in the configuration file named config.toml, in gitlabe-runner volume.


### ENJOY!!!
