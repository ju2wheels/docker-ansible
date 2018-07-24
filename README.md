# docker-ansible

[docker-ansible](https://github.com/ju2wheels/docker-ansible) provides [ju2wheels/ansible](https://hub.docker.com/r/ju2wheels/ansible/) Docker Hub
images for various Linux distribution images with Ansible 1.x/2.x and core module dependencies installed from PyPi using Python 2.7 at the user
level instead of at the system level so as to minimize conflicts with system Python packages.

The goal of these images is to provide a container that is capable of being used for both unit testing (by running Ansible against the local
container as if it were a remote machine) as well as being suitable for use as an Ansible host.

## Available Docker Image Tags

The `ju2wheels/ansible` Docker image tags follow the naming convention that includes the following items joined with `-`:

1. The Ansible major version (ie `1.x` or `2.x` since we always install the latest minor version for each).
2. The Linux distribution name.
3. The Linux distribution version.

|1.x Docker Image Tags  |
|-----------------------|
|1.x-alpine-3.3         |
|1.x-alpine-3.4         |
|1.x-alpine-3.5         |
|1.x-alpine-3.6         |
|1.x-alpine-3.7         |
|1.x-alpine-3.8         |
|1.x-amazonlinux-2016.09|
|1.x-amazonlinux-2017.03|
|1.x-amazonlinux-2017.09|
|1.x-amazonlinux-2017.12|
|1.x-amazonlinux-2018.03|
|1.x-centos-6           |
|1.x-centos-7           |
|1.x-debian-7           |
|1.x-debian-8           |
|1.x-debian-9           |
|1.x-fedora-20          |
|1.x-fedora-21          |
|1.x-fedora-22          |
|1.x-fedora-23          |
|1.x-fedora-24          |
|1.x-fedora-25          |
|1.x-fedora-26          |
|1.x-fedora-27          |
|1.x-fedora-28          |
|1.x-linuxmint-17       |
|1.x-linuxmint-18       |
|1.x-linuxmint-19       |
|1.x-opensuse-42.2      |
|1.x-opensuse-42.3      |
|1.x-ubuntu-12.04       |
|1.x-ubuntu-14.04       |
|1.x-ubuntu-16.04       |
|1.x-ubuntu-18.04       |


|2.x Docker Image Tags  |
|-----------------------|
|2.x-alpine-3.3         |
|2.x-alpine-3.4         |
|2.x-alpine-3.5         |
|2.x-alpine-3.6         |
|2.x-alpine-3.7         |
|2.x-alpine-3.8         |
|2.x-amazonlinux-2016.09|
|2.x-amazonlinux-2017.03|
|2.x-amazonlinux-2017.09|
|2.x-amazonlinux-2017.12|
|2.x-amazonlinux-2018.03|
|2.x-centos-6           |
|2.x-centos-7           |
|2.x-debian-7           |
|2.x-debian-8           |
|2.x-debian-9           |
|2.x-fedora-20          |
|2.x-fedora-21          |
|2.x-fedora-22          |
|2.x-fedora-23          |
|2.x-fedora-24          |
|2.x-fedora-25          |
|2.x-fedora-26          |
|2.x-fedora-27          |
|2.x-fedora-28          |
|2.x-linuxmint-17       |
|2.x-linuxmint-18       |
|2.x-linuxmint-19       |
|2.x-opensuse-42.2      |
|2.x-opensuse-42.3      |
|2.x-ubuntu-12.04       |
|2.x-ubuntu-14.04       |
|2.x-ubuntu-16.04       |
|2.x-ubuntu-18.04       |

Note: The Alpine 3.3 and 3.4 Docker images dont have `shadow-utils` available to them, so this has been backported from Alpine 3.5 so that
the `user` Ansible module still works.

## Organization of `Dockerfile`s

Each image `Dockerfile` has its commands organized as follows:

1. Set environment variables for `PATH` and any environment variables required for building the Python modules we will install.
2. System updates (update all packages that came in the base distro image).
3. Supplement repository setup.
4. Install base development tools and any packages that we want included in our images to make Ansible work.
5. Install development libraries that are required to build Python modules we want to install (including Ansible) but that we intend to remove.
6. Install pip, Ansible, and other Ansible dependencies from PyPi at the user level (root).
7. Uninstall the development libraries required to install Python modules.
8. Delete caches and temporary files.
9. Set the default `entrypoint` to `ansible-playbook`.

Note: We install Ansible at the user level instead of a virtualenv because some of the Python modules can only be installed via distro packages
and not from PyPi. Therefore by installing a global Python 2.7 on the distro and those dependencies using the system packaging we can still access
them by installing Ansible and all other dependencies at the user level while not cluttering up the system level Python packages or potentially
crippling the system.

## Using The Containers As Ansible Hosts

By default, all the images have their `entrypoint` configured as `ansible-playbook` for use as unit test containers.

In order to run the container as an Ansible host you will have to do the following:

1. Override the `entrypoint` to a proper shell such as `/bin/bash`.
2. Mount your Ansible playbook directory as a `VOLUME`.
3. Set the `ANSIBLE_CONFIG` and optionally the `ANSIBLE_INVENTORY` environment variables.

Using the CLI:

```
docker run --entrypoint /bin/bash                                   \
           --env ANSIBLE_CONFIG=/ansible-playbook/ansible.cfg       \
           --env ANSIBLE_INVENTORY=/ansible-playbook/inventory      \
           --volume '/home/user/ansible-playbook:/ansible-playbook' \
           -it ju2wheels/ansible:<tag> <ansible-playbook ARGS> <playbook.yml>
```


Using a `docker-compose` file:

```
version: '2'
services:
  ansible_host:
    entrypoint: /bin/bash
    environment:
      ANSIBLE_CONFIG: /ansible-playbook/ansible.cfg
      ANSIBLE_INVENTORY: /ansible-playbook/inventory
    image: ju2wheels/ansible:<tag>
    tty: true
    volumes:
      # If you place this docker-compose.yml in the root of your ansible-playbook directory
      # then you can make the volume path relative instead of absolute
      #- ./:/ansible-playbook
      - /home/user/ansible-playbook:/ansible-playbook
```


You can then run `docker-compose`:

```
docker-compose run ansible_host
cd /ansible-playbook
ansible-playbook my-playbook.yml
```

## Using The Containers For Ansible Role Unit Testing

For the following unit test examples, we assume that your Ansible role meets the following conditions:

1. The role is modeled after an Ansible 2.x role as created by `ansible-galaxy init`, for example:
    ```
    $ ansible-galaxy init testrole
    $ find test
    testrole
    testrole/README.md
    testrole/defaults
    testrole/defaults/main.yml
    testrole/handlers
    testrole/handlers/main.yml
    testrole/meta
    testrole/meta/main.yml
    testrole/tasks
    testrole/tasks/main.yml
    testrole/tests
    testrole/tests/inventory
    testrole/tests/test.yml
    testrole/vars
    testrole/vars/main.yml
    ```
2. The role's tests directory has had an ansible.config and inventory added, and roles directory with a role that is relatively symlinked back to the main role directory:
    ```
    $ cd testrole/tests/
    
    $ cat <<EOF > ansible.cfg
    [default]
    # At a minimum, inventory and roles variables need to be defined
    inventory = ./inventory
    roles = ./roles
    [privilege_escalation]
    # Docker only has su available by default
    become_method=su
    EOF

    $ cat <<EOF > inventory
    # At a minimum, we need localhost and we need to set ansible_python_interpreter
    # because not all the Docker images default to Python 2.7 as the default Python
    localhost ansible_connection=local ansible_python_interpreter=/usr/bin/python2.7
    EOF

    $ mkdir roles
    $ cd roles
    $ ln -s ../.././testrole
    ```


Using the above role structure, all we have to do is add a `docker_test.yml` playbook file to our role's `tests/` directory that
runs the `docker_container` module (Ansible 2.x) or `docker` module (Ansible 1.x) to execute the `test.yml` playbook inside of
one of our Docker containers.

Using Ansible 1.x `docker_test.yml` may look like this:

```
---

- hosts: localhost
  tasks:
    - name: testrole dockerized unit test
      docker: >
        command=/ansible-playbook/tests/test.yml
        detach=false
        entrypoint=ansible-playbook
        env={"ANSIBLE_CONFIG": "/ansible-playbook/tests/ansible.cfg", "ANSIBLE_INVENTORY": "/ansible-playbook/tests/inventory", "ANSIBLE_NOCOLOR": 1}
        hostname=ansible_testrole_test
        image={{ item }}
        name=ansible_testrole_test
        pull=true
        restart_policy=false
        state=started
        tty=true
        volumes=["{{ playbook_dir }}/../:/ansible-playbook"]
      with_items:
        - ju2wheels/ansible:1.x-ubuntu-12.04
        - ju2wheels/ansible:1.x-ubuntu-14.04
        - ju2wheels/ansible:1.x-ubuntu-16.04
```


Using Ansible 2.x `docker_test.yml` may look like this:

```
---

- hosts: localhost
  tasks:
    - name: testrole dockerized unit test
      docker_container:
        cleanup: true
        command: /ansible-playbook/tests/test.yml
        detach: false
        entrypoint: ansible-playbook
        env:
          ANSIBLE_CONFIG:    /ansible-playbook/tests/ansible.cfg
          ANSIBLE_INVENTORY: /ansible-playbook/tests/inventory
          ANSIBLE_NOCOLOR:   1
        hostname: ansible_testrole_test
        image: "{{ item }}"
        interactive: true
        name: ansible_testrole_test
        pull: true
        recreate: true
        restart_policy: false
        state: started
        tty: true
        volumes:
          - "{{ playbook_dir }}/../:/ansible-playbook"
      with_items:
        - ju2wheels/ansible:2.x-ubuntu-12.04
        - ju2wheels/ansible:2.x-ubuntu-14.04
        - ju2wheels/ansible:2.x-ubuntu-16.04
```

You can then run `docker_test.yml` to kick off your unit tests:

```
cd testrole/tests
ansible-playbook docker_test.yml
```

Note: In order to run the the unit tests, you will need the following installed on the host running the tests:

* ansible
* docker
* docker Python module (or docker-py for older versions of Docker)

See the [ju2wheels.pyenv](https://github.com/ju2wheels/ansible-galaxy-ju2wheels.pyenv/tree/master/tests) Ansible Galaxy role unit test
for a more concrete example.

Note: I have tried to ensure all Ansible core module dependencies are installed in these images, however, since I can't test each individual module
there may be instances where dependencies may have been missed. If you encounter a missing dependency or would like to see dependencies for commonly
used third party Ansible modules, please open an [issue](https://github.com/ju2wheels/docker-ansible/issues) and include the Ansible version you are
using, the Docker image name, the Ansible module name, and a description of the dependencies required by that module.

## Running Ansible As Another User

Since Ansible is installed at the user level, only the root user in these containers can run Ansible.

If you want to add another user under which to run Ansible you will have to copy the root user's `HOME` directory:

```
useradd -m newuser
cp -ar /root/. /home/newuser/
chown -R newuser:newuser /home/newuser
echo 'export PATH=/home/newuser/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin' >> /home/newuser/.bashrc
```

## Contributing

Contributions of additional platforms or updates to Ansible module dependencies are welcome. Please open an
[issue](https://github.com/ju2wheels/docker-ansible/issues) first before submitting a PR.

## License

GPLv2

## Author

Julio Lajara \<GH user at Gmail>
