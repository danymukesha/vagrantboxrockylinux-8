# vagrantboxrockylinux-8
Creating a vagrant box rockylinux 8

Download vagrant first

<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/532435ec-ae8f-427b-9799-191aa57f1eff" width="500" />
 
Choose the version which compatible with your computer architecture

<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/9ad32718-cc09-4678-b5b5-65524ddf5df1" width="500" />

Complete the installation instructions

Create a new working directory for the new virtual machine
 
<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/23b46071-941b-494b-a023-570be9255409" width="200" />
 
Create Vagrantfile in working directory by running this command:
```
vagrant init rockylinux/8
```
The you should have the following vagrant file created in the directory
 
Vagrantfile
```
Vagrant.configure("2") do |config|
  config.vm.box = "rockylinux/8"
  config.vm.provider "virtualbox" do |domain|
    domain.customize ["modifyvm", :id, "--firmware", "efi"]
  end
end
```
Create bugfix box metadata file named box-metadata.json in working directory:

```
{
  "name" : "rockylinux/8",
  "description" : "Rocky Linux 8 7.0.0 Bugfix",
  "versions" : [
    {
      "version" : "7.0.1-20221213.0",
      "providers" : [
        {
          "name" : "virtualbox",
          "url" : "http://dl.rockylinux.org/pub/rocky/8/images/x86_64/Rocky-8-Vagrant-Vbox-8.7-20221213.0.x86_64.box"
        }
      ]
    }
  ]
}
```
 
Add bugfix box:
```
vagrant box add box-metadata.json
```

<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/14a217f4-4c44-4e44-b9d2-762c03455393" width="600" />
 

Bring up the box:
```
vagrant up
```
<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/dca920f1-f74f-4f3a-ad79-2a0c2313cd5f" width="600" />

<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/34c556f3-ee01-4e0e-839f-3946ed4f3ab5" width="600" />

Then the virtual machine running in *background* is created successfully

<img src="https://github.com/danymukesha/vagrantboxrockylinux-8/assets/45208254/cf2c8079-c782-4d56-b1aa-4f72336a60a0" width="500" />

 
