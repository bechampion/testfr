Vagrant.configure("2") do |config|
    config.vm.define "opendjserver" do | ldapserver | 
        config.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        ldapserver.vm.box = "centos/7"
        ldapserver.vm.network "private_network", ip: "172.16.5.11"
        ldapserver.vm.provision "ansible" do |ansible|
            ansible.playbook = "opendj.yml"
            ansible.verbose = ""
        end
    end
    config.vm.define "openamserver" do | openamserver | 
        config.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        openamserver.vm.box = "centos/7"
        openamserver.vm.network "private_network", ip: "172.16.5.12"
        openamserver.vm.provision "ansible" do |ansible|
            ansible.playbook = "openam.yml"
            ansible.verbose = ""
        end
    end
end


