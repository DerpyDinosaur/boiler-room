## Connections

### SSH

Public and Private keys can be used to connect via `ssh`. 
Use SSH Keygen to create the public and private key, since they will be used in automation contexts an empty password is preferred. 

- `ssh-keygen`
- *Enter folder to store the public and private key*
- *Enter password*
- *Then copy the public key to the `ssh` `authorized_keys` file on the machine you wish to connect to*

### GitHub Actions

A secret will be required to be made in the GitHub repo that contains the whole private key. This way any GitHub Ansible Workflow can run on the machines you are targeting. 

## Docker

Run to build the image in docker `docker build . --tag test:latest`

Run to run the container and forward the port 22 `docker run --rm -p 22:22 test`