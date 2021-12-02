# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "thinhho/automation-macos"

  # Use NFS for the shared folder
  config.vm.synced_folder ".", "/vagrant", default: true

  # NFS needs host-only network
  config.vm.network :private_network, ip: "172.16.2.42"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "macosx-test"
    vb.memory = 4096
    vb.cpus = 2

    # Display the VirtualBox GUI when booting the machine
    # Show gui, incl. some power
    vb.gui = true

    # Some needed OSX configs
    vb.customize ["modifyvm", "macosx-test", "--cpuid-set", "00000001", "000106e5", "00100800", "0098e3fd", "bfebfbff"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct", "iMac19,1"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion", "1.0"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct", "Mac-AA95B1DDAB278B95"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal/Devices/smc/0/Config/DeviceKey", "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC", "1"]
    vb.customize ["setextradata", "macosx-test", "VBoxInternal2/EfiGopMode", "5"]
  
    # Customize the amount of memory on the VM:
    vb.memory = "4096"
    vb.cpus = "2"
  end

  # Copy folder across from local machine to VM - This line was for testing my ansible playbook located - 
  # https://github.com/devunderslash/mac-setup-stripped/blob/main/README.md
  # config.vm.provision "file", source: ".", destination: "~/Users/vagrant/"

  # config.vm.provision "shell", path: "~./WorkMac-Playbook/run_setup.sh"

  # # Run ansible playbook from ~/remote/vagrant/WorkMac-Playbook
  #   # Run Ansible from the Vagrant VM
  # config.vm.provision "ansible_local" do |ansible|
  #   ansible.playbook = "remote/vagrant/WorkMac-Playbook/main.yml"
  # end

end
