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
        config.vm.provision "file", source: "/vagrant/vagrant/AM-eval-5.0.0.zip", destination: "/vagrant/AM-eval-5.0.0.zip"
        openamserver.vm.box = "centos/7"
        openamserver.vm.network "private_network", ip: "172.16.5.12"
        openamserver.vm.provision "ansible" do |ansible|
            ansible.playbook = "openam.yml"
            ansible.verbose = ""
        end
    end
    config.vm.define "openigserver" do | openigserver | 
        config.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        config.vm.provision "file", source: "/vagrant/vagrant/IG-5.0.0.war", destination: "/vagrant/IG-5.0.0.war"
        openigserver.vm.box = "centos/7"
        openigserver.vm.network "private_network", ip: "172.16.5.13"
        openigserver.vm.provision "ansible" do |ansible|
            ansible.playbook = "openig.yml"
            ansible.verbose = ""
        end
    end
end


