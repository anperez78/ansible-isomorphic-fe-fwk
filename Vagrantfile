# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = "hashicorp/precise64"
  config.vm.network :private_network, 
                    :auto_config => true, 
                    :ip => "192.168.100.30", 
                    :netmask => "255.255.0.0"
  config.ssh.forward_agent = true

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/playbook.yml"
    ansible.galaxy_role_file = "provision/requirements.yml"
    ansible.galaxy_roles_path = "provision/roles/"
    ansible.verbose = true
  end
end
