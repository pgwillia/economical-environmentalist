# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos6.5"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.hostname = "econ-env.local"

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  config.vm.provision "shell", inline: "yum install -y yum-utils"
  config.vm.provision "shell", inline: "yum install -y python-ipython-notebook  scipy python-matplotlib Mayavi sympy python-networkx pexpect python-nose python-setuptools python-sphinx python-pygments python-pandas python-argparse"
  config.vm.provision "shell", inline: "yum-builddep -y python scipy python-matplotlib Mayavi Cython"
  config.vm.provision "shell", inline: "ipython notebook --ip 192.168.33.10 --notebook-dir /vagrant &"

end
