# k8s-vagrant-wsl
Kubernetes cluster using Vagrant and Windows Subsystem for Linux

## Pre-requisites (Tested Setup)

* Oracle VirtualBox 6.1
* Windows Subsystem for Linux (Ubuntu 18.04)
* Vagrant 2.2.7 (Installed in WSL)

## Using it

Create a folder ```C:\k8s```

Clone the repository and put the content into ```C:\k8s```

Define the following variables (replace <wsl_user> with your WSL user name):
```
export VAGRANT_WSL_WINDOWS_ACCESS_USER_HOME_PATH=/home/<wsl_user>/k8s
export VAGRANT_WSL_ENABLE_WINDOWS_ACCESS="1"
export PATH="$PATH:/mnt/c/Program Files/Oracle/VirtualBox"
```

Adjust the number of K8S Workers to be used inside Vagrantfile (standard is N = 2).

Adjust the number of cores and memory for each node (standard is 2CPUs/2048MB):
```
    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end
```

Finally, execute ```vagrant up``` and wait for approx. 15 minutes.
