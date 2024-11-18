This is a playground for testing out Ansible. It consists of 2 docker container:
- ansible: this is the contaner where ansible is running
- playground: this is the container where ansible executes

When running, we setup the hosts user and group ids, so that when we create files and folder in ansible we can edit them from the host.

Start the docker containers with:
```bash
MY_UID="$(id -u)" MY_GID="$(id -g)" docker compose up
```

Example how to create a tempalte for a fole:
```bash
docker compose exec ansible ansible-galaxy init <role name>
```

Example how to run a playbook:
```bash
docker compose exec ansible ansible-playbook playbooks/ping.yml
```