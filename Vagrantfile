Vagrant.configure("2") do |config|

    config.vm.provider "virtualbox" do |v|
        v.memory = 1024
        v.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate//v-root", "1"]
        v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--nictype1", "Am79C973"]
    end

    config.vm.define "trusty64" do |trusty64|
        trusty64.vm.box = "ubuntu/trusty64"
        trusty64.vm.hostname = "devbox-trusty64"
        trusty64.vm.network "private_network", ip: "10.1.1.8"
        trusty64.vm.provision :shell, path: "provision.sh"
    end

end

