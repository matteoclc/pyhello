# PyHello
### Requirements
* One (control node and worker together) or two Linux hosts
* Ansible to deploy the application (on the control node)
* Docker to build the image and run the container (worker)
* Python3 pip on the worker to install dependencies
* Git (optional) to clone the repo

### Setup the environment
#### Get the app
Clone this repository 

$ git clone https://github.com/matteoclc/pyhello.git

or download the zip file

https://github.com/matteoclc/pyhello/archive/refs/heads/main.zip

#### Configure target host
The deploy will be done via Ansible, for this to work you need to specify where to build and run the PyHello app. Edit the **inventory** file and write the hostname of the target server (worker group), if you want to build and run on the ansible control node you can leave it as it is ( *localhost* ).

#### Install and configure Ansible
This tasks is out of the scope of this documentation but you can refer here
https://docs.ansible.com/ansible/2.9/installation_guide/index.html

You'll have to end up with a working installation of ansible and connection to the target host (with root/sudo permissions) where you want to run the application.

#### Install and configure Docker
As above, you can follow this instructions to install Docker
https://docs.docker.com/desktop/linux/install/

### Deploy the application
Once you are ready you can simply start the deploy by executing the deploy.sh script

$ ./deploy.sh

In case of successfull installation the playbook will end with a message like this

    TASK [Final message] ***********************************************************************************
    ok: [localhost] => {
        "msg": "PyHello is alive! you can check at http://192.168.88.1:5000/hello"
    }


