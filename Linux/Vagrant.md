# vagrant 便捷的虚拟机管理工具

https://blog.csdn.net/imilano/article/details/83038682
https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v
https://learn.hashicorp.com/tutorials/vagrant/getting-started-up?in=vagrant/getting-started
https://www.vagrantup.com/docs/installation


# 本地vagrant 虚拟机 
C:\Users\2294765\Desktop\MyWork\VMs



# 在本地部署k8s集群

C:\Users\2294765\Desktop\MyWork\VMs\K8sClusers\kubernetes-vagrant-centos-cluster



![image-20201229180411255](C:\Users\2294765\AppData\Roaming\Typora\typora-user-images\image-20201229180411255.png)

## vagrant cloud

https://app.vagrantup.com/generic/boxes/centos8

# Install and Specify a Box
```
>mkdir vagrant_getting_started
>cd vagrant_getting_started
>vagrant init hashicorp/bionic64
```

# Add Box(ubantu )
```
#C:\Users\2294765\Desktop\MyWork\DevDocs\OpenSource\vagrant_getting_started

>vagrant box add hashicorp/bionic64
```
```
#Use a Box
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
end

```


## Bring up a virtual machine
```
>vagrant up
```
## SSH into the machine
```
>vagrant ssh
```
## »Remove the box

```
vagrant box list
vagrant box remove hashicorp/bionic64
```
## Suspend the machine
```
>vagrant suspend
```

## »Halt the machine
```
>vagrant halt
```

## »Destroy the machine
```
The vagrant destroy command does not remove the downloaded box file. List your box files.

>vagrant destroy
```