Vagrant.configure("2") do |config|
    config.vm.box = "bento/centos-7.2"

    # Run ansible from the Vagrant VM
    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "provisioning/playbook.yml"
    end

end
