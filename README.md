# Multipass Usage Doc  - BRIDGES
Multipass Commands Document

## Create Bridged Interface
Utilize Netplan to create a bridged interface in the physcial interface (remember the name, below we will use br1 as an example)

You will need to create all bridges in Netplan first and then use the following command to get them into the Multipass namespace

    multipass launch --network br1

## Create Ubuntu VM with Bridged Interface
    multipass launch -n <vm-name> -d <disk-size> -m <memory-size> --network name=pubBr;mode=manual --cloud-init <cloud-config-file> <image-name>

Replace <vm-name> with the desired name for your VM, <disk-size> with the desired size of the VM's disk in gigabytes, <memory-size> with the desired amount of memory in megabytes, <cloud-config-file> with the path to a cloud-config file containing any additional setup you want to perform on the VM, and <image-name> with the name of the Ubuntu image you want to use (e.g. "20.04" for Ubuntu 20.04 LTS)

## Create Ubuntu VM with TWO Bridges Interfaces

    multipass launch -n <vm-name> -d <disk-size> -m <memory-size> --network name=pubBr;mode=manual --network name=prvBr;mode=manual --cloud-init <cloud-config-file> <image-name>

Replace <vm-name> with the desired name for your VM, <disk-size> with the desired size of the VM's disk in gigabytes, <memory-size> with the desired amount of memory in megabytes, <cloud-config-file> with the path to a cloud-config file containing any additional setup you want to perform on the VM, and <image-name> with the name of the Ubuntu image you want to use (e.g. "20.04" for Ubuntu 20.04 LTS)